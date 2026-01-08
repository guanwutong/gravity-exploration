# 如何在网站中插入Word文档

## 方法一：直接链接到Word文档（推荐）

这是最简单直接的方法，适用于当前网站的资源卡片结构。

### 步骤：

1. **准备Word文档**
   - 将您的Word文档命名为有意义的名称（如：`lesson7-1-teaching-design.docx`）
   - 确保文档内容完整且格式正确

2. **上传文档到网站目录**
   - 将Word文档复制到网站根目录（与`index.html`同一级）
   - 建议创建一个`documents`文件夹来存放所有文档，保持目录整洁

3. **修改卡片中的链接**
   - 打开课时页面文件（如：`lesson7-1.html`）
   - 找到卡片中的链接代码：`<a href="#">查看详情</a>`
   - 将链接地址修改为文档的相对路径

### 示例代码：

```html
<!-- 示例：链接到教学设计文档 -->
<div class="resource-card">
    <h3>教学设计</h3>
    <p>包含详细的教学目标、教学重难点、教学过程和教学反思。</p>
    <a href="documents/lesson7-1-teaching-design.docx">查看详情</a>
</div>

<!-- 示例：链接到教学课件文档 -->
<div class="resource-card">
    <h3>教学课件</h3>
    <p>包含精心设计的PPT课件，帮助学生更好地理解知识点。</p>
    <a href="documents/lesson7-1-teaching-ppt.docx">查看详情</a>
</div>

<!-- 示例：链接到巩固提升文档 -->
<div class="resource-card">
    <h3>巩固提升</h3>
    <p>提供精选练习题，帮助学生巩固所学知识，提升解题能力。</p>
    <a href="documents/lesson7-1-exercises.docx">查看详情</a>
</div>
```

## 方法二：将Word文档转换为HTML嵌入

如果您希望在网页中直接显示文档内容，可以将Word文档转换为HTML格式。

### 步骤：

1. **将Word文档转换为HTML**
   - 打开Word文档
   - 点击"文件" → "另存为" → 选择"网页（*.htm; *.html）"格式
   - 保存生成的HTML文件

2. **嵌入到网页中**
   - 可以直接将HTML内容复制到课时页面中
   - 或者使用iframe标签嵌入整个HTML文件

### 示例代码（使用iframe）：

```html
<!-- 示例：使用iframe嵌入HTML文档 -->
<div class="resource-card">
    <h3>教学设计</h3>
    <p>包含详细的教学目标、教学重难点、教学过程和教学反思。</p>
    <a href="#" onclick="showDocument('documents/lesson7-1-teaching-design.html')">查看详情</a>
</div>

<!-- 在页面底部添加显示文档的div -->
<div id="document-container" style="display: none;">
    <iframe id="document-iframe" width="100%" height="600px"></iframe>
    <button onclick="hideDocument()">关闭文档</button>
</div>

<script>
function showDocument(url) {
    document.getElementById('document-iframe').src = url;
    document.getElementById('document-container').style.display = 'block';
}

function hideDocument() {
    document.getElementById('document-container').style.display = 'none';
    document.getElementById('document-iframe').src = '';
}
</script>
```

## 方法三：使用在线文档服务嵌入

您还可以使用Google Docs或Microsoft OneDrive等在线服务来嵌入文档。

### 步骤：

1. **上传文档到在线服务**
   - 将Word文档上传到Google Docs或Microsoft OneDrive
   - 设置文档的共享权限（允许任何人查看）

2. **获取嵌入链接**
   - 在Google Docs中：点击"文件" → "发布到网络" → "嵌入" → 复制嵌入代码
   - 在Microsoft OneDrive中：点击"共享" → "嵌入" → 复制嵌入代码

3. **嵌入到网页中**
   - 将复制的嵌入代码粘贴到网页中

### 示例代码（Google Docs）：

```html
<!-- 示例：嵌入Google Docs文档 -->
<div class="resource-card">
    <h3>教学设计</h3>
    <p>包含详细的教学目标、教学重难点、教学过程和教学反思。</p>
    <iframe src="https://docs.google.com/document/d/e/2PACX-1vR5Y5Y8K_8Q7Z6Z6Z6Z6Z6Z6Z6Z6Z6Z6Z6Z6Z6Z6Z6Z6Z6Z6Z6Z/pub?embedded=true" width="100%" height="400"></iframe>
</div>
```

## 实际应用示例

以`lesson7-1.html`为例，修改后的资源卡片代码：

```html
<div class="resource-cards">
    <div class="resource-card">
        <h3>教学设计</h3>
        <p>包含详细的教学目标、教学重难点、教学过程和教学反思。</p>
        <a href="documents/lesson7-1-teaching-design.docx">查看详情</a>
    </div>
    <div class="resource-card">
        <h3>教学课件</h3>
        <p>包含精心设计的PPT课件，帮助学生更好地理解知识点。</p>
        <a href="documents/lesson7-1-teaching-ppt.pptx">查看详情</a>
    </div>
    <div class="resource-card">
        <h3>巩固提升</h3>
        <p>提供精选练习题，帮助学生巩固所学知识，提升解题能力。</p>
        <a href="documents/lesson7-1-exercises.docx">查看详情</a>
    </div>
</div>
```

## 注意事项

1. **文件命名**：使用英文名称，避免中文和特殊字符，以免出现链接错误
2. **文件大小**：Word文档不宜过大（建议不超过10MB），否则会影响加载速度
3. **浏览器兼容性**：不同浏览器对Word文档的处理方式不同，有些会直接下载，有些会在线预览
4. **更新维护**：如果文档内容需要更新，记得同时更新网站上的文件

希望这些方法能帮助您顺利在网站中插入Word文档！