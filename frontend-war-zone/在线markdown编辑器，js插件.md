<div>
<p>
	<strong>Editor.md</strong>是一个基于jQuery和<a target="_blank" href="http://www.oschina.net/p/codemirror">CodeMirror</a>构建的在线Markdown文档编辑器。
</p>
<p>
	<img src="http://static.oschina.net/uploads/img/201502/10093913_Ze1K.jpg" alt="editormd-screenshot" title="editormd-screenshot" data-bd-imgshare-binded="1"> 
</p>
<h4>
	主要特性<br>
</h4>
<ul>
	<li>
		<p>
			支持Markdown标准和Github风格；
		</p>
	</li>
	<li>
		<p>
			支持实时预览、图片（跨域）上传和多语言语法高亮；
		</p>
	</li>
	<li>
		<p>
			兼容主流的浏览器（IE8+）和Zepto.js，且支持iPad等平板设备；
		</p>
	</li>
	<li>
		<p>
			支持<a href="https://pandao.github.io/editor.md/examples/toc.html">ToC（Table of Contents）</a>；
		</p>
	</li>
	<li>
		<p>
			支持识别和解析HTML标签，具有几乎无限的扩展性；
		</p>
	</li>
	<li>
		<p>
			支持TeX科学公式（基于<a href="https://pandao.github.io/editor.md/examples/katex.html">KaTeX</a>）；
		</p>
	</li>
	<li>
		<p>
			支持流程图flowchart和时序图sequenceDiagram;
		</p>
	</li>
	<li>
		<p>
			支持AMD/CMD模块化加载（支持<a href="https://pandao.github.io/editor.md/examples/use-requirejs.html">Require.js</a>&amp;<a href="https://pandao.github.io/editor.md/examples/use-seajs.html">Sea.js</a>）；
		</p>
	</li>
</ul>
<h4>
	在线演示
</h4>
<p>
	<a href="https://pandao.github.io/editor.md/examples/index.html">https://pandao.github.io/editor.md/examples/index.html</a> 
</p>
<h4>
	下载和安装
</h4>
<p>
	通过Github下载安装，或者通过bower安装：
</p>
<div><div id="highlighter_850377" class="syntaxhighlighter  shell"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="gutter"><div class="line number1 index0 alt2">1</div></td><td class="code"><div class="container"><div class="line number1 index0 alt2"><code class="shell plain">bower&nbsp;</code><code class="shell functions">install</code>&nbsp;<code class="shell plain">editor.md</code></div></div></td></tr></tbody></table></div></div>
<h4>
	使用方法
</h4>
<p>
	HTML：
</p>
<div><div id="highlighter_429073" class="syntaxhighlighter  html"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="gutter"><div class="line number1 index0 alt2">1</div><div class="line number2 index1 alt1">2</div><div class="line number3 index2 alt2">3</div><div class="line number4 index3 alt1">4</div></td><td class="code"><div class="container"><div class="line number1 index0 alt2"><code class="html plain">&lt;</code><code class="html keyword">link</code>&nbsp;<code class="html color1">rel</code><code class="html plain">=</code><code class="html string">"stylesheet"</code>&nbsp;<code class="html color1">href</code><code class="html plain">=</code><code class="html string">"../dist/css/editormd.css"</code>&nbsp;<code class="html plain">/&gt;</code></div><div class="line number2 index1 alt1"><code class="html plain">&lt;</code><code class="html keyword">div</code>&nbsp;<code class="html color1">id</code><code class="html plain">=</code><code class="html string">"test-editormd"</code><code class="html plain">&gt;</code></div><div class="line number3 index2 alt2"><code class="html spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="html plain">&lt;</code><code class="html keyword">textarea</code><code class="html plain">&gt;###Hello&nbsp;world!&lt;/</code><code class="html keyword">textarea</code><code class="html plain">&gt;</code></div><div class="line number4 index3 alt1"><code class="html plain">&lt;/</code><code class="html keyword">div</code><code class="html plain">&gt;</code></div></div></td></tr></tbody></table></div></div>
<p>
	提示1：如果没有Markdown源内容或者通过Ajax异步加载Markdown源文档等，可以不添加&lt;textarea&gt;，会自动添加；
</p>
<p>
	提示2：如果不想出现textarea闪现，则在textarea加上 style="display:none;"；
</p>
<p>
	javascript:
</p>
</div>
