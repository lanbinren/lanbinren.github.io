title: hexo优化
date: 2018/12/20 11:05:25
---


优化参考 网站
https://segmentfault.com/a/1190000009544924
https://reuixiy.github.io/technology/computer/computer-aided-art/2017/06/09/hexo-next-optimization.html#%E9%99%84%E4%B8%8A%E6%88%91%E7%9A%84-custom-styl



<div>
    {% if not is_index %}
        <div style="text-align:center;color: #636363;font-size:14px;letter-spacing: 10px">本文结束啦<i class="fa fa-bell"></i>感谢您的阅读</div>
    {% endif %}
</div>

在 \themes\next\layout\_macro 新建 passage-end-tag.swig 文件

打开更新文章 时间
themes\next\_config.yml
{% codeblock %}
post_meta:
  item_text: true
  created_at: true
  updated_at: true//false
  categories: true
{% endcodeblock %}


显示统计字数和估计阅读时长 需要增加如下插件
{% codeblock %}
npm install hexo-wordcount --save
{% endcodeblock %}


Local search
{% codeblock %}
npm install hexo-generator-searchdb --save
{% endcodeblock %}


使用图床保留图片七牛云 

参照修改
https://yangbingdong.com/2017/build-blog-hexo-advanced/#%E5%AE%9A%E4%BD%8D%E5%85%83%E7%B4%A0
1,侧栏加入已运行的时间

背景图片
