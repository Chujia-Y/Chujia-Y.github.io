# 个人网站：手动更新指南

网站地址：https://chujia-y.github.io/  
GitHub 仓库：https://github.com/Chujia-Y/Chujia-Y.github.io

这是一个无需安装软件、无需构建的静态网站。GitHub Pages 从仓库的 main 分支根目录发布。所有带方括号的文字都是待替换的占位内容；圆形头像目前也是占位图。

## 1. 每个文件负责什么

| 文件 | 需要修改的内容 |
| --- | --- |
| index.html | 首页姓名、身份、学校、邮箱、简介、研究兴趣和教育信息 |
| research.html | 研究经历、项目、职位、日期和成果 |
| cv.html | 网页版 CV；上传 PDF 后可在这里添加下载链接 |
| about.html | 性格、价值观和爱好 |
| profile.svg | 当前的头像占位图；上传真实照片后可不再使用 |
| style.css | 字体、颜色、间距和手机布局 |
| favicon.svg | 浏览器标签上的小图标 |

## 2. 在 GitHub 网页上修改文字

1. 登录 GitHub，打开上面的仓库地址，确认当前分支是 **main**。
2. 在文件列表中点击要修改的文件，例如 **index.html**。
3. 点击文件右上角的铅笔图标 **Edit this file**。
4. 找到方括号中的占位内容，直接替换文字。保留周围的 HTML 标签，例如 <p>、<h1>、<li> 和 </li>。
5. 点击右上角 **Commit changes...**，写一句说明，例如 “Update home page information”。
6. 选择直接提交到 **main**，再点击 **Commit changes**。
7. 等待 GitHub Pages 完成更新，然后刷新 https://chujia-y.github.io/ 查看效果。

首页姓名出现在页眉、头像下方、浏览器标题等位置。请在 **index.html** 中都改成同一个姓名；另外三个 HTML 文件的页眉和浏览器标题也请同步修改。

**邮箱要改两处：** 在 **index.html** 中，把显示出来的 your.email@example.com 和链接中的 mailto:your.email@example.com 都替换为你的公开邮箱。例如：

~~~html
<a class="profile-email" href="mailto:name@university.edu">name@university.edu</a>
~~~

## 3. 换成自己的照片

1. 准备一张你有权公开使用的照片，建议用正方形 JPG，文件名为 **profile.jpg**。网站会自动裁成圆形。
2. 在仓库首页选择 **Add file → Upload files**，选中照片，填写提交说明，然后提交到 **main**。
3. 打开 **index.html** 并点击铅笔图标，把这一行中的 profile.svg 改为 profile.jpg，同时修改替代文字：

~~~html
<img class="portrait" src="profile.jpg" alt="Portrait of Your Name">
~~~

4. 提交修改并刷新网站。原有 profile.svg 可以留在仓库，不影响显示。

## 4. 上传 CV 的 PDF

1. 把 PDF 命名为 **cv.pdf**。在仓库首页选择 **Add file → Upload files**，上传并提交到 **main**。
2. 打开 **cv.html**，找到含有 “A downloadable PDF CV can be added here later” 的段落。
3. 将整个段落替换为：

~~~html
<p><a class="pdf-link" href="cv.pdf" target="_blank" rel="noopener">Download my CV (PDF)</a></p>
~~~

4. 提交后打开 CV 页面，点击链接，确认 PDF 能正常打开。若以后更新 CV，继续上传同名的 cv.pdf 覆盖原文件即可。

## 5. 新增一条研究经历

打开 **research.html**。每一条经历都是从 <article class="entry"> 到对应 </article> 的完整段落。复制其中一整段，在下一条经历前粘贴，然后修改日期、标题、机构、角色和描述。示例：

~~~html
<article class="entry">
  <div class="entry-date">[Month Year – Month Year]</div>
  <div>
    <h2>[Research project or position title]</h2>
    <p class="entry-place">[Institution or research group] · [Your role]</p>
    <p>[Question, methods, your contribution, and outcome.]</p>
  </div>
</article>
~~~

## 6. 修改“About Myself”

打开 **about.html**。第一段可写性格或自我介绍；“How I work and connect with others” 可写你与人合作的方式；“Outside of research” 可写爱好。把方括号和其中的提示文字一起替换掉即可。

## 7. 正式填写资料后允许搜索引擎收录

目前四个 HTML 页面都有这一行，作用是避免占位版本被搜索引擎收录：

~~~html
<meta name="robots" content="noindex, nofollow">
~~~

真实资料全部填好后，分别编辑 **index.html、research.html、cv.html、about.html**，删除这行并提交。网站本身在删除之前也能通过网址直接访问。

## 8. 如果改错了

在仓库首页点击 **Commits**，找到修改前的提交，可以查看旧内容。修改少量文字时，也可以重新编辑文件，再提交一次；GitHub Pages 会使用最新的 main 分支内容。

参考 GitHub 官方操作说明：

- 编辑文件：https://docs.github.com/en/repositories/working-with-files/managing-files/editing-files
- 上传文件：https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
- 设置 Pages 发布源：https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
