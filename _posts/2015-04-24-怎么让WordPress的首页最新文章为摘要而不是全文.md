---
layout: article
title: 怎么让WordPress的首页最新文章为摘要而不是全文
description: 解决使用wordpress的主题时首页全文显示的问题
category: tech
---

>  摘要： {{page.description}}

---

##背景：

出现的问题：由于文章太长，将全文摆放在首页难看且浪费网络资源，查询百度后，发现有以下解决方案。该方案是针对WordPress的Twenty Twelve主题进行的修改，其他主题都类似修改.

##哪里编辑
WordPress准许用户在`外观->编辑`中修改本WordPress使用的主题。打开`控制台->外观->编辑->index.php`可以看到以下代码

        <?php /* Start the Loop */ ?>
        <?php while ( have_posts() ) : the_post(); ?>
            <?php get_template_part( 'content', get_post_format() ); ?>
        <?php endwhile; ?>

        
这段代码的意思是在首页index.php页面将文章呈现出来，使用content.php 模板显示这些内容。因此打开`content.php`的编辑页面，找到下面的代码
        
        <div class="entry-content">
            <?php the_content( __( 'Continue reading <span class="meta-nav">&rarr;</span>', 'twentytwelve' ) ); ?>
            <?php wp_link_pages( array( 'before' => '<div class="page-links">' . __( 'Pages:', 'twentytwelve' ), 'after' => '</div>' ) ); ?>
        </div><!-- .entry-content -->

##如何修改

将Continue reading这一段给注释掉，替代成下面的代码
    
        <?php if(!is_single()) {
            the_excerpt();
        } else {
            the_content(__('(more…)'));
        } ?>   
    
保存之后，打开首页就可以只看摘要了。
    
