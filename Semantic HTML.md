<div class="page">
  




<p>“Semantic HTML” refers to the idea that all your HTML markup should convey
the underlying meaning of your content—not its appearance. We’ve already
  been writing semantic HTML (e.g., using <a href="/html-and-css/basic-web-pages/#structure-versus-presentation"><code>&lt;strong&gt;</code>
    instead of <code>&lt;b&gt;</code></a>), but there’s a whole set of elements
  designed for the sole purpose of adding more meaning to the overall layout of
  a web page. They’re called “sectioning elements”, and they look something
  like this:</p>

<img src="https://internetingishard.com/html-and-css/semantic-html/html-sectioning-elements-00c3fd.png">

<p>Using these as an alternative to <code>&lt;div&gt;</code> elements is an
important aspect of modern web development because it makes it easier for
search engines, screen readers, and other machines to identify the different
parts of your website. It also helps you as a developer keep your site
organized, which, in turn, makes it easier to maintain.</p>


<img src="https://internetingishard.com/html-and-css/semantic-html/semantic-html-ffab7c.png">

<p>We’re going back to straight HTML this chapter—no <a href="/html-and-css/css-box-model/">box model</a>, <a href="/html-and-css/flexbox/">flexbox</a>, or <a href="/html-and-css/advanced-positioning">positioning schemes</a>. However,
that’s not to say you can’t apply all of the CSS rules from previous chapters
to these new elements. Think of sectioning elements as
<code>&lt;div&gt;</code>’s, but with <em>meaning</em>.</p>

</div></div>


<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="setup"><span style="background-color: rgb(254, 254, 254); box-shadow: rgb(254, 254, 254) 11px 0px 0px, rgb(254, 254, 254) -13px 0px 0px;">Setup</span></h2></div>

<p>Our example for this chapter will be a simple unstyled HTML document. Create
a new <a href="/html-and-css/introduction/#atom-text-editor">Atom project</a>
called <code>semantic-html</code> with a new file in it called
<code>article.html</code>. Add the following:</p>

<pre class="highlight"><code><span class="hljs-meta">&lt;!DOCTYPE html&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">html</span> <span class="hljs-attr">lang</span>=<span class="hljs-string">'en'</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">head</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">meta</span> <span class="hljs-attr">charset</span>=<span class="hljs-string">'UTF-8'</span>/&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">title</span>&gt;</span>Semantic HTML<span class="hljs-tag">&lt;/<span class="hljs-name">title</span>&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">head</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">body</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Interneting Is Easy!<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">ul</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Home<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>About<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Blog<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Sign Up<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
    <span class="hljs-tag">&lt;/<span class="hljs-name">ul</span>&gt;</span>

  <span class="hljs-tag">&lt;/<span class="hljs-name">body</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">html</span>&gt;</span>
</code></pre>

<p>That <code>&lt;h1&gt;</code> and <code>&lt;ul&gt;</code> are presumably the
top-level banner for our website—not the main content of the web page.
We’ve never had to make this distinction before, but that’s what
this whole chapter is about.</p>

</div></div>


<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="the-document-outline"><span style="background-color: rgb(254, 254, 254); box-shadow: rgb(254, 254, 254) 11px 0px 0px, rgb(254, 254, 254) -13px 0px 0px;">The Document Outline</span></h2></div>

<p>Every HTML document has an “outline,” which is how search
engines and screen readers view the hierarchy of the content on the page. The
<code>&lt;h1&gt;</code> through <code>&lt;h6&gt;</code> <a href="/html-and-css/basic-web-pages/#headings">heading elements</a> all
contribute to a page’s document outline. Let’s check it out by
adding a dummy blog post to our <code>article.html</code> file:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Semantic HTML<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>By Troy McClure. Published January 3rd<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>This is an example web page explaining HTML5 semantic markup.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>

<span class="hljs-tag">&lt;<span class="hljs-name">h2</span>&gt;</span>The Document Outline<span class="hljs-tag">&lt;/<span class="hljs-name">h2</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>HTML5 includes several “sectioning content” elements that
   affect the document outline.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>

<span class="hljs-tag">&lt;<span class="hljs-name">h3</span>&gt;</span>Headers<span class="hljs-tag">&lt;/<span class="hljs-name">h3</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>The <span class="hljs-tag">&lt;<span class="hljs-name">code</span>&gt;</span>&amp;lt;header&amp;gt;<span class="hljs-tag">&lt;/<span class="hljs-name">code</span>&gt;</span> element is one such sectioning
   element.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>

<span class="hljs-tag">&lt;<span class="hljs-name">h3</span>&gt;</span>Footers<span class="hljs-tag">&lt;/<span class="hljs-name">h3</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>And so is the <span class="hljs-tag">&lt;<span class="hljs-name">code</span>&gt;</span>&amp;lt;footer&amp;gt;<span class="hljs-tag">&lt;/<span class="hljs-name">code</span>&gt;</span> element.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>

<span class="hljs-tag">&lt;<span class="hljs-name">h2</span>&gt;</span>Inline Semantic HTML<span class="hljs-tag">&lt;/<span class="hljs-name">h2</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>The <span class="hljs-tag">&lt;<span class="hljs-name">code</span>&gt;</span>&amp;lt;time&amp;gt;<span class="hljs-tag">&lt;/<span class="hljs-name">code</span>&gt;</span> element is semantic, but it’s not
   sectioning content.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>

<span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>This fake article was written by somebody at InternetingIsHard.com, which
   is a pretty decent place to learn how to become a web developer.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>

<span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>&amp;copy; 2017 InternetingIsHard.com<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
</code></pre>

<p>The <a href="https://gsnedders.html5.org/outliner/">HTML5 Outliner</a> is a
convenient tool for inspecting the document outline of a page. Go ahead and
paste the entirety of <code>article.html</code> into the text field at the
bottom. You should see the outline for our example, which currently has the
following structure. It’s a little reminiscent of the research paper
outlines you learned to make in elementary school.</p>


<img src="https://internetingishard.com/html-and-css/semantic-html/document-outline-heading-elements-576433.png">

<p>Each <code>&lt;h1&gt;</code> element creates a new section in the document
outline, and any less prominent headings that follow it are considered
  subsections under that top-level heading. E.g., the <strong>Semantic
    HTML</strong> section has two subsections in it: <strong>The&nbsp;Document
    Outline</strong> and <strong>Inline&nbsp;Semantic HTML</strong>. The same
  goes for <code>&lt;h2&gt;</code> and <code>&lt;h3&gt;</code> elements, and so
  on down to <code>&lt;h6&gt;</code>.</p>

<p>Note that the actual value of the heading level doesn’t matter:
what’s important is whether or not it’s greater than or less than
the heading of the current section. For example, change the
<code>&lt;h3&gt;</code> headings to <code>&lt;h4&gt;</code> and run it
through the outliner tool again. Since the <code>&lt;h4&gt;</code> is still
less than the parent <code>&lt;h2&gt;</code>, this shouldn’t have any
affect on the document outline.</p>


<img src="https://internetingishard.com/html-and-css/semantic-html/document-outline-section-creation-45ee48.png">

<p>How’s this document outline stuff relate to semantic HTML? Well,
headings are some of the most semantic things in a web page. They play a
significant role in how search engines determine what’s important in your
web page. In addition, the semantic HTML elements we’re about to cover
add more meaning to and sometimes even alter the default outlining behavior
discussed here.</p>

</div></div>


<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="articles"><span style="background-color: rgb(253, 253, 254); box-shadow: rgb(253, 253, 254) 11px 0px 0px, rgb(253, 253, 254) -13px 0px 0px;">Articles</span></h2></div>

<p>The <code>&lt;article&gt;</code> element represents an independent article
in a web page. It should only wrap content that can be plucked out of your page
and distributed in a completely different context. For instance, an app like <a href="https://flipboard.com/" target="_blank">Flipboard</a> should be able to
grab an <code>&lt;article&gt;</code> element from your site, display it in
its own app, and have it make perfect sense to its readers.</p>


<img src="https://internetingishard.com/html-and-css/semantic-html/html-article-element-82490e.png">

<p>In our example, we can use <code>&lt;article&gt;</code> to mark the main
content of the page as a self-contained unit, like so:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">article</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Semantic HTML<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>By Troy McClure. Published January 3rd<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>This is an example web page explaining HTML5 semantic markup.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-comment">&lt;!-- ... --&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>This fake article was written by somebody at InternetingIsHard.com, which
     is a pretty decent place to learn how to become a web developer.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">article</span>&gt;</span>

<span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>&amp;copy; 2017 InternetingIsHard.com<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
</code></pre>

<p>Notice how we left the copyright notice <em>outside</em> the
<code>&lt;article&gt;</code> element because it’s a footer for the entire
site—not specifically for our article. As we’ll discover shortly,
<code>&lt;article&gt;</code>’s are essentially mini web pages in
your HTML document. They have their own headers, footers, and document outline
that are completely isolated from the rest of your site.</p>


<div class="subsubheading content__subsubheading"><h3 class="subsubheading__heading" id="using-multiple-article-elements">Using Multiple Article Elements</h3></div>

<p>For things like blog posts, newspaper articles, or web pages dedicated to a
single topic, there’s often only one <code>&lt;article&gt;</code> element on
the page. But, it’s perfectly legal to have more than one
<code>&lt;article&gt;</code> element per page. A good example is a page that
displays a bunch of blog posts. Each one of them can be wrapped in a separate
set of <code>&lt;article&gt;</code> tags (you don’t need to add this to our
<code>article.html</code> page):</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">article</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>First Post<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>Some content<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">article</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">article</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Second Post<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>Some more content<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">h2</span>&gt;</span>Subsection<span class="hljs-tag">&lt;/<span class="hljs-name">h2</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>Some details<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">article</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">article</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Last Post<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>Final bit of content<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">article</span>&gt;</span>
</code></pre>

<p>This tells anybody looking at our page that there are three distinct articles
that can be syndicated. Think of it as a way to merge multiple HTML files into
a single document without confusing search engines, browsers, or other machines
that are trying to parse our content.</p>

<p>Compare this to a bunch of generic <code>&lt;div&gt;</code> elements with
arbitrary class names, and you can begin to see how semantic HTML makes the Web
a much easier place to navigate.</p>

</div></div>


<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="sections"><span style="background-color: rgb(253, 253, 253); box-shadow: rgb(253, 253, 253) 11px 0px 0px, rgb(253, 253, 253) -13px 0px 0px;">Sections</span></h2></div>

<p>The <code>&lt;section&gt;</code> element is sort of like an
<code>&lt;article&gt;</code>, except it doesn’t need to make sense
outside the context of the document. That is, an app like Flipboard
wouldn’t try to pull out all the <code>&lt;section&gt;</code>’s of
your page and present them as independent pieces of content.</p>

<img src="https://internetingishard.com/html-and-css/semantic-html/html-section-element-92a4d1.png">

<p>Think of <code>&lt;section&gt;</code> as an <em>explicit</em> way to define
the sections in a document outline. Why would we want this instead of letting
the heading levels do it for us? Often times, you need a container to wrap a
section for layout purposes, and it makes sense to use the more descriptive
<code>&lt;section&gt;</code> element over a generic
<code>&lt;div&gt;</code>.</p>

<p>Let’s section off two parts of our <code>article.html</code> file:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">section</span>&gt;</span>     <span class="hljs-comment">&lt;!-- Add this --&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">h2</span>&gt;</span>The Document Outline<span class="hljs-tag">&lt;/<span class="hljs-name">h2</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>HTML5 includes several “sectioning content” elements that
     affect the document outline.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>

  <span class="hljs-tag">&lt;<span class="hljs-name">h3</span>&gt;</span>Headers<span class="hljs-tag">&lt;/<span class="hljs-name">h3</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>The <span class="hljs-tag">&lt;<span class="hljs-name">code</span>&gt;</span>&amp;lt;header&amp;gt;<span class="hljs-tag">&lt;/<span class="hljs-name">code</span>&gt;</span> element is one such sectioning
     element.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>

  <span class="hljs-tag">&lt;<span class="hljs-name">h3</span>&gt;</span>Footers<span class="hljs-tag">&lt;/<span class="hljs-name">h3</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>And so is the <span class="hljs-tag">&lt;<span class="hljs-name">code</span>&gt;</span>&amp;lt;footer&amp;gt;<span class="hljs-tag">&lt;/<span class="hljs-name">code</span>&gt;</span> element.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">section</span>&gt;</span>    <span class="hljs-comment">&lt;!-- And this --&gt;</span>

<span class="hljs-tag">&lt;<span class="hljs-name">section</span>&gt;</span>     <span class="hljs-comment">&lt;!-- This too! --&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">h2</span>&gt;</span>Inline Semantic HTML<span class="hljs-tag">&lt;/<span class="hljs-name">h2</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>The <span class="hljs-tag">&lt;<span class="hljs-name">code</span>&gt;</span>&amp;lt;time&amp;gt;<span class="hljs-tag">&lt;/<span class="hljs-name">code</span>&gt;</span> element is semantic, but it’s not
     sectioning content.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">section</span>&gt;</span>    <span class="hljs-comment">&lt;!-- Don't forget this --&gt;</span>
</code></pre>

<p>This keeps our document outline the exact same while lending it some extra
semantic structure, as well as a nice hook for any CSS styles we might want to
apply (e.g., a background color for a particular section).</p>

<div class="subsubheading content__subsubheading"><h3 class="subsubheading__heading" id="section-and-the-document-outline">&lt;section&gt; and the Document Outline</h3></div>

<p>The previous change also has an interesting side effect on the implicit
sectioning behavior of our headings. Watch what happens when we bump the
second <code>&lt;h2&gt;</code> down to a much lower heading level:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">section</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">h6</span>&gt;</span>Inline Semantic HTML<span class="hljs-tag">&lt;/<span class="hljs-name">h6</span>&gt;</span>     <span class="hljs-comment">&lt;!-- Change this heading level --&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>The <span class="hljs-tag">&lt;<span class="hljs-name">code</span>&gt;</span>&amp;lt;time&amp;gt;<span class="hljs-tag">&lt;/<span class="hljs-name">code</span>&gt;</span> element is semantic, but it’s not
  sectioning content.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">section</span>&gt;</span>
</code></pre>

<p>The <code>&lt;h6&gt;</code> is lower than the <code>&lt;h3&gt;</code> that
precedes it, so you might expect it to become part of the
<strong>Footer</strong> section. But, that’s not the case: the document
outline is still the exact same as before.</p>

<img src="https://internetingishard.com/html-and-css/semantic-html/sections-and-document-outline-614f12.png">


<p>By adding those <code>&lt;section&gt;</code> elements, we’re telling
the document outline that it should be defined by the nesting structure of the
<code>&lt;section&gt;</code> elements instead of the heading levels. This
basically means that each <code>&lt;section&gt;</code> can have its own
set of <code>&lt;h1&gt;</code> through <code>&lt;h6&gt;</code> headings that are
independent of the rest of the page.</p>

<p>However, you shouldn’t use the <code>&lt;section&gt;</code> element to
manipulate the document outline in this way because browsers, screen readers,
and some search engines don’t properly interpret the effect of
<code>&lt;section&gt;</code> on the document outline. Instead, always define a
page’s outline via heading levels, using <code>&lt;section&gt;</code>
only as a replacement for container <code>&lt;div&gt;</code>’s when
appropriate.</p>

<p>Also note that each <code>&lt;section&gt;</code> element should contain at
least one heading, otherwise it will add an “untitled section” to
your document outline. As an example, try updating
<code>article.html</code> to match the following, then run it through
the outliner tool again:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">h2</span>&gt;</span>Inline Semantic HTML<span class="hljs-tag">&lt;/<span class="hljs-name">h2</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">section</span>&gt;</span>
  <span class="hljs-comment">&lt;!-- This will be an "Untitled Section" --&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>The <span class="hljs-tag">&lt;<span class="hljs-name">code</span>&gt;</span>&amp;lt;time&amp;gt;<span class="hljs-tag">&lt;/<span class="hljs-name">code</span>&gt;</span> element is semantic, but it’s not
  sectioning content.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">section</span>&gt;</span>
</code></pre>

<p>This creates a new section, but since there’s no heading associated
with it, the document outline doesn’t know what to call it. This should
generally be avoided when using <code>&lt;section&gt;</code> elements.</p>


<img src="https://internetingishard.com/html-and-css/semantic-html/untitled-section-in-document-outline-b511bc.png">

<p>As defined by the HTML5 specification, <code>&lt;section&gt;</code> is a
pretty generic element. That, plus the fact that browsers and screen readers
can’t properly interpret its role in document outlines makes it difficult
to know when and how to leverage it properly. Our advice is to only use
<code>&lt;section&gt;</code> as a more descriptive <code>&lt;div&gt;</code>
wrapper for the implicitly defined sections of your page. Don’t use it
for self-contained content (that’s what <code>&lt;article&gt;</code> is
for) or when it’s <a href="#divs-for-layout"><em>purely</em> for layout
purposes</a>.</p>

</div></div>


<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="nav-elements"><span style="background-color: rgb(252, 252, 253); box-shadow: rgb(252, 252, 253) 11px 0px 0px, rgb(252, 252, 253) -13px 0px 0px;">Nav Elements</span></h2></div>

<p>The <code>&lt;nav&gt;</code> element lets you mark up the various navigation
sections of your website. This goes for the main site navigation, links to related
pages in a sidebar, tables of content, and pretty much any group of links. For
example, we should stick our site-wide navigation menu in a
<code>&lt;nav&gt;</code> element:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Interneting Is Easy!<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">nav</span>&gt;</span>                                    <span class="hljs-comment">&lt;!-- Add this --&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">ul</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Home<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>About<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Blog<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Sign Up<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">ul</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">nav</span>&gt;</span>                                    <span class="hljs-comment">&lt;!-- This too! --&gt;</span>
</code></pre>

<p>This is a great piece of semantic information for search engines. It helps
them quickly identify the structure of your entire website, making it easier to
discover other pages. As we’ll see in <a href="#asides">Asides</a>,
it’s possible to include multiple <code>&lt;nav&gt;</code> elements on a
single page if you have different sets of related links.</p>


<img src="https://internetingishard.com/html-and-css/semantic-html/html-nav-element-d1e716.png">

</div></div>


<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="headers"><span style="background-color: rgb(252, 252, 253); box-shadow: rgb(252, 252, 253) 11px 0px 0px, rgb(252, 252, 253) -13px 0px 0px;">Headers</span></h2></div>

<p>The <code>&lt;header&gt;</code> element is a new piece of semantic markup,
not to be confused with head<em>ings</em> (the
<code>&lt;h1&gt;</code>-<code>&lt;h6&gt;</code> elements). It denotes
introductory content for a section, article, or entire web page.
“Introductory content” can be anything from your company’s
logo to navigational aids or author information.</p>


<img src="https://internetingishard.com/html-and-css/semantic-html/html-header-element-7b4e01.png">

<p>It’s a best practice to wrap a website’s name/logo
and main navigation in a <code>&lt;header&gt;</code>, so let’s go ahead
and add one to our example project:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">header</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Interneting Is Easy!<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">nav</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">ul</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Home<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>About<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Blog<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Sign Up<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
    <span class="hljs-tag">&lt;/<span class="hljs-name">ul</span>&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">nav</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">header</span>&gt;</span>
</code></pre>

<p>Headers are only associated with the nearest sectioning
element—typically a <code>&lt;body&gt;</code>,
<code>&lt;section&gt;</code>, or <code>&lt;article&gt;</code> element. This
means that you can use multiple <code>&lt;header&gt;</code> elements to add
introductory content to different parts of a document. For instance, the title,
author, and publication date of our <code>&lt;article&gt;</code> is a pretty
good candidate for another <code>&lt;header&gt;</code>:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">article</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">header</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Semantic HTML<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>By Troy McClure. Published January 3rd<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">header</span>&gt;</span>

  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>This is an example web page explaining HTML5 semantic markup.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-comment">&lt;!-- ... --&gt;</span>
</code></pre>

<p class="nudge-desktop--smaller">Without this <code>&lt;header&gt;</code>,
search engines and screen readers wouldn’t know that first
<code>&lt;p&gt;</code> was separate from the main content of the article. Like
<code>&lt;section&gt;</code>, it also serves as a convenient CSS hook, since
the title and author info for a blog post are often styled differently than the
rest of the article. Again, think of <code>&lt;header&gt;</code> as a more
semantic alternative to a <code>&lt;div&gt;</code> container.</p>

</div></div>

<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="footers"><span style="background-color: rgb(251, 252, 252); box-shadow: rgb(251, 252, 252) 11px 0px 0px, rgb(251, 252, 252) -13px 0px 0px;">Footers</span></h2></div>

<p>Conceptually, footers are basically the same as headers, except they
generally come at end of an article/website opposed to the beginning. Common
use cases include things like copyright notices, footer navigation, and author
bios at the end of blog posts.</p>


<img src="https://internetingishard.com/html-and-css/semantic-html/html-footer-element-0c927a.png">

<p>Footers behave the same as <code>&lt;header&gt;</code> in that they’re
associated with the nearest sectioning element. So, we can use it for our
page’s copyright notice and the author information inside our
<code>&lt;article&gt;</code>. Add the following two footer elements to our
<code>article.html</code> page:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">article</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">header</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Semantic HTML<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>By Troy McClure. Published January 3rd<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">header</span>&gt;</span>

  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>This is an example web page explaining HTML5 semantic markup.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-comment">&lt;!-- ... --&gt;</span>
  
  <span class="hljs-tag">&lt;<span class="hljs-name">footer</span>&gt;</span>         <span class="hljs-comment">&lt;!-- Add this --&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>This fake article was written by somebody at InternetingIsHard.com,
       which is a pretty decent place to learn how to become a web developer. This
       footer is only for the containing <span class="hljs-tag">&lt;<span class="hljs-name">code</span>&gt;</span>&amp;lt;article&amp;gt;<span class="hljs-tag">&lt;/<span class="hljs-name">code</span>&gt;</span> element.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">footer</span>&gt;</span>        <span class="hljs-comment">&lt;!-- And this --&gt;</span>

<span class="hljs-tag">&lt;/<span class="hljs-name">article</span>&gt;</span>

<span class="hljs-tag">&lt;<span class="hljs-name">footer</span>&gt;</span>           <span class="hljs-comment">&lt;!-- This, too --&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>&amp;copy; 2017 InternetingIsHard.com<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">footer</span>&gt;</span>          <span class="hljs-comment">&lt;!-- Don't forget to close it! --&gt;</span>

<span class="hljs-tag">&lt;/<span class="hljs-name">body</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">html</span>&gt;</span>
</code></pre>

<p>The <code>&lt;footer&gt;</code> inside the <code>&lt;article&gt;</code>
element is only for the contents of that article, which makes sense because it
contains the author’s bio. The second footer, on the other hand, is
connected to the entire page.</p>

</div></div>


<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="asides"><span style="background-color: rgb(251, 251, 252); box-shadow: rgb(251, 251, 252) 11px 0px 0px, rgb(251, 251, 252) -13px 0px 0px;">Asides</span></h2></div>

<p>Headers and footers are ways to add extra information to an article, but
sometimes we want to <em>remove</em> information from an article. For example,
a sponsored blog post might contain an advertisement about the sponsoring
company; however, we probably don’t want to make it part of the article
text. This is what the <code>&lt;aside&gt;</code> element is for.</p>

<img src="https://internetingishard.com/html-and-css/semantic-html/html-aside-element-ce120b.png">

<p>Let’s add a fake advertisement to our <code>article.html</code> file,
right underneath the article’s header:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">article</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">header</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Semantic HTML<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>By Troy McClure. Published January 3rd<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">header</span>&gt;</span>
  <span class="hljs-comment">&lt;!-- Look! A fake advertisement! --&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">aside</span> <span class="hljs-attr">class</span>=<span class="hljs-string">'advert'</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">img</span> <span class="hljs-attr">src</span>=<span class="hljs-string">'some-advert-image.png'</span>/&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">aside</span>&gt;</span>
  
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>This is an example web page explaining HTML5 semantic markup.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
</code></pre>

<p>Even though the image is inside the <code>&lt;article&gt;</code> element,
machine readers know that it’s only tangentially related to the article
content. In addition to advertisements, <code>&lt;aside&gt;</code> is also
appropriate for highlighting definitions, stats, or quotations. If it looks
different than the rest of the article, chances are it’s an aside.</p>

<p>When used <em>outside</em> an <code>&lt;article&gt;</code>, an
<code>&lt;aside&gt;</code> is associated with the page as a whole (much like
<code>&lt;header&gt;</code> and <code>&lt;footer&gt;</code>). This makes it a
good choice for marking up a site-wide sidebar. Add the following underneath
the closing <code>&lt;/article&gt;</code> tag, before the second
<code>&lt;footer&gt;</code>:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">aside</span> <span class="hljs-attr">class</span>=<span class="hljs-string">'sidebar'</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">h2</span>&gt;</span>Sidebar<span class="hljs-tag">&lt;/<span class="hljs-name">h2</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>Some sidebar content<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">nav</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">h3</span>&gt;</span>HTML &amp;amp; CSS Tutorial<span class="hljs-tag">&lt;/<span class="hljs-name">h3</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">ul</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Introduction<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Basic Web Pages<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>etc...<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
    <span class="hljs-tag">&lt;/<span class="hljs-name">ul</span>&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">nav</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">nav</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">h3</span>&gt;</span>JavaScript Tutorial<span class="hljs-tag">&lt;/<span class="hljs-name">h3</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">ul</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Introduction<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Hello, JavaScript<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>etc...<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
    <span class="hljs-tag">&lt;/<span class="hljs-name">ul</span>&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">nav</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">aside</span>&gt;</span>
</code></pre>

<p>Notice the <code>class</code> attributes in both of these snippets. If we
were worried about CSS this chapter, we could style our
<code>&lt;aside&gt;</code> elements in exactly the same way as all the
<code>&lt;div&gt;</code>’s we’ve been working with throughout this
tutorial. Which brings us to…</p>

</div></div>


<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="divs-for-layout"><span style="background-color: rgb(250, 251, 252); box-shadow: rgb(250, 251, 252) 11px 0px 0px, rgb(250, 251, 252) -13px 0px 0px;">Divs For Layout</span></h2></div>

<p>You should use semantic HTML whenever you can, since it helps machines infer
the structure of your content, and it gives you a standardized vocabulary to
organize your web pages. However, sometimes you need a container element when
none of the semantic HTML elements we just covered would make sense.
There’s nothing wrong with using a plain old <code>&lt;div&gt;</code>
purely for layout purposes.</p>

<p>For instance, if we want to center our page using that familiar <a href="/html-and-css/css-box-model/#aligning-boxes">auto-margin
technique</a>, we have to wrap the whole page in a container.
It’s entirely presentational, so a <code>&lt;div&gt;</code> is the best
option:</p>

<pre class="highlight"><code>  <span class="hljs-tag">&lt;<span class="hljs-name">body</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">div</span> <span class="hljs-attr">class</span>=<span class="hljs-string">'page'</span>&gt;</span>             <span class="hljs-comment">&lt;!-- Start of container div --&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">header</span>&gt;</span>
        <span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Interneting Is Easy!<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
        <span class="hljs-tag">&lt;<span class="hljs-name">nav</span>&gt;</span>
          <span class="hljs-tag">&lt;<span class="hljs-name">ul</span>&gt;</span>
            <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Home<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
            <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>About<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
            <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Blog<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
            <span class="hljs-tag">&lt;<span class="hljs-name">li</span>&gt;</span><span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'#'</span>&gt;</span>Sign Up<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">li</span>&gt;</span>
          <span class="hljs-tag">&lt;/<span class="hljs-name">ul</span>&gt;</span>
        <span class="hljs-tag">&lt;/<span class="hljs-name">nav</span>&gt;</span>
      <span class="hljs-tag">&lt;/<span class="hljs-name">header</span>&gt;</span>
      <span class="hljs-comment">&lt;!-- ... --&gt;</span>
      <span class="hljs-tag">&lt;<span class="hljs-name">footer</span>&gt;</span>
        <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>&amp;copy; 2017 InternetingIsHard.com<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
      <span class="hljs-tag">&lt;/<span class="hljs-name">footer</span>&gt;</span>
    <span class="hljs-tag">&lt;/<span class="hljs-name">div</span>&gt;</span>                         <span class="hljs-comment">&lt;!-- End of container div --&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">body</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">html</span>&gt;</span>
</code></pre>

<p>This is particularly relevant for <a href="/html-and-css/flexbox/">flexbox</a>, as it
requires lots of <code>&lt;div&gt;</code>’s to group flex items
correctly. Occasionally, you may find that a <code>&lt;section&gt;</code> or
<code>&lt;nav&gt;</code> is
appropriate for these flex items, but it’s pretty common to find a bunch
of presentational <code>&lt;div&gt;</code> elements in a flexbox layout.</p>

<p>The point is, don’t use semantic elements just for the sake of using
them. Implementing them incorrectly is worse than not using them at all, so if
you’re ever in doubt, use a <code>&lt;div&gt;</code> instead.</p>

</div></div>


<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="dates-and-times"><span style="background-color: rgb(250, 251, 251); box-shadow: rgb(250, 251, 251) 11px 0px 0px, rgb(250, 251, 251) -13px 0px 0px;">Dates and Times</span></h2></div>

<p>For humans, dates and times come in many forms. You can refer to January
3rd, 2017 as “1/3/2017”, “Jan 3rd”, or even
“yesterday” depending on the current date. Parsing this kind of
ambiguous natural language is difficult and error-prone for machines, which is
where <code>&lt;time&gt;</code> comes in.</p>

<p>The <code>&lt;time&gt;</code> element represents either a time of day or a
calendar date. Providing a machine-readable date makes it possible for browsers
to automatically link it to users’ calendars and helps search engines
clearly identify specific dates. A simple Google search will show you the
effect of including a <code>&lt;time&gt;</code> element on your page:</p>


<img src="https://internetingishard.com/html-and-css/semantic-html/time-element-in-google-search-results-5bba38.png">

<p>Let’s make the publish date of our article unambiguous by wrapping it
in <code>&lt;time&gt;</code> tags:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">article</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">header</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">h1</span>&gt;</span>Semantic HTML<span class="hljs-tag">&lt;/<span class="hljs-name">h1</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>By Troy McClure. Published <span class="hljs-tag">&lt;<span class="hljs-name">time</span> <span class="hljs-attr">datetime</span>=<span class="hljs-string">'2017-1-3'</span>&gt;</span>January
       3rd<span class="hljs-tag">&lt;/<span class="hljs-name">time</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">header</span>&gt;</span>
  <span class="hljs-comment">&lt;!-- ... --&gt;</span>
</code></pre>

<p>The machine-readable date is defined in the <code>datetime</code> attribute.
An easy way to remember the date format is that it goes from largest time
period to smallest: year, month, then date. Note that even though the year
isn’t included in the human-readable text, this tells search engines that
our article was published in 2017.</p>

<img src="https://internetingishard.com/html-and-css/semantic-html/datetime-format-d0c825.png">

<p>It’s possible to include times and time zones inside of
<code>datetime</code>, too. If we wanted to add a 3:00pm PST time to our
publish date, we’d use the following:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">time</span> <span class="hljs-attr">datetime</span>=<span class="hljs-string">'2017-1-3 15:00-0800'</span>&gt;</span>January 3rd<span class="hljs-tag">&lt;/<span class="hljs-name">time</span>&gt;</span>
</code></pre>

<p>The time itself is in 24-hour format, and the <code>-0800</code> is the time
zone offset from GMT (in this case, <code>-0800</code> represents Pacific
Standard Time).</p>

</div></div>


<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="address"><span style="background-color: rgb(250, 250, 251); box-shadow: rgb(250, 250, 251) 11px 0px 0px, rgb(250, 250, 251) -13px 0px 0px;">Address</span></h2></div>

<p>The <code>&lt;address&gt;</code> element is like <code>&lt;time&gt;</code>
in that it doesn’t deal with the overall structure of a document, but
rather embellishes the parent <code>&lt;article&gt;</code> or
<code>&lt;body&gt;</code> element with some metadata. It defines contact
information for the author of the article or web page in question.
<code>&lt;address&gt;</code> should <em>not</em> be used for arbitrary physical
addresses.</p>

<p>For instance, maybe we want to add an author email address in our
article’s footer:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">footer</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>This fake article was written by somebody at InternetingIsHard.com, which
     is a pretty decent place to learn how to become a web developer. This footer
     is only for the containing <span class="hljs-tag">&lt;<span class="hljs-name">code</span>&gt;</span>&amp;lt;article&amp;gt;<span class="hljs-tag">&lt;/<span class="hljs-name">code</span>&gt;</span> element.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">address</span>&gt;</span>
    Please contact <span class="hljs-tag">&lt;<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">'mailto:troymcclure@example.com'</span>&gt;</span>Troy
    McClure<span class="hljs-tag">&lt;/<span class="hljs-name">a</span>&gt;</span> for questions about this article.
  <span class="hljs-tag">&lt;/<span class="hljs-name">address</span>&gt;</span>
<span class="hljs-tag">&lt;/<span class="hljs-name">footer</span>&gt;</span>
</code></pre>

<p>By default, this will be styled the same way as <code>&lt;em&gt;</code>, but
you can change that with a simple CSS rule. Also notice the new email link in the
  <code>href</code>, which you can read more about at <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Email_links">Mozilla
    Developer Network</a>.</p>

</div></div>

<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="figures-and-captions"><span style="background-color: rgb(249, 250, 251); box-shadow: rgb(249, 250, 251) 11px 0px 0px, rgb(249, 250, 251) -13px 0px 0px;">Figures and Captions</span></h2></div>

<p>Last, but certainly not least, are the <code>&lt;figure&gt;</code> and
<code>&lt;figcaption&gt;</code> elements. The former represents a
self-contained “figure”, like a diagram, illustration, or even a
code snippet. The latter is optional, and it associates a caption with its
parent <code>&lt;figure&gt;</code> element.</p>

<p>A common use case for both of these is to add visible descriptions to the
<code>&lt;img/&gt;</code> elements in an article, like so:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">section</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">h2</span>&gt;</span>The Document Outline<span class="hljs-tag">&lt;/<span class="hljs-name">h2</span>&gt;</span>
  <span class="hljs-tag">&lt;<span class="hljs-name">p</span>&gt;</span>HTML5 includes several “sectioning content” elements that
    affect the document outline.<span class="hljs-tag">&lt;/<span class="hljs-name">p</span>&gt;</span>

  <span class="hljs-tag">&lt;<span class="hljs-name">figure</span>&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">img</span> <span class="hljs-attr">src</span>=<span class="hljs-string">'semantic-elements.png'</span>
         <span class="hljs-attr">alt</span>=<span class="hljs-string">'Diagram showing &lt;article&gt;, &lt;section&gt;, and &lt;nav&gt; elements'</span>/&gt;</span>
    <span class="hljs-tag">&lt;<span class="hljs-name">figcaption</span>&gt;</span>New HTML5 semantic elements<span class="hljs-tag">&lt;/<span class="hljs-name">figcaption</span>&gt;</span>
  <span class="hljs-tag">&lt;/<span class="hljs-name">figure</span>&gt;</span>
  <span class="hljs-comment">&lt;!-- ... --&gt;</span>
</code></pre>

<p>The <a href="/html-and-css/links-and-images/#text-alternatives"><code>alt</code>
attribute</a> is closely related to the
<code>&lt;figcaption&gt;</code> element. <code>alt</code> should serve as a
text <em>replacement</em> for the image, while <code>&lt;figcaption&gt;</code> is
a supporting <em>description</em> displayed with either the image or its
text-based equivalent.</p>

<p>When using <code>&lt;figcaption&gt;</code> in the above manner, you can
safely omit an image’s <code>alt</code> attribute without hurting your
SEO. Depending on what kind of images you’re working with, it may be more
convenient (and less redundant) to have visible
<code>&lt;figcaption&gt;</code>’s that describe them opposed to invisible
<code>alt</code> attributes.</p>

</div></div>

<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="css-legacy-considerations"><span style="background-color: rgb(249, 250, 251); box-shadow: rgb(249, 250, 251) 11px 0px 0px, rgb(249, 250, 251) -13px 0px 0px;">CSS/Legacy Considerations</span></h2></div>

<p>And finally, a quick note on legacy browsers. The semantic HTML elements in
this chapter were introduced in HTML5. All modern browser recognize them
without any extra work, but you’ll often see something like the following
in global CSS stylesheets:</p>

<pre class="highlight"><code><span class="hljs-selector-tag">section</span>, <span class="hljs-selector-tag">article</span>, <span class="hljs-selector-tag">aside</span>, <span class="hljs-selector-tag">footer</span>, <span class="hljs-selector-tag">header</span>, <span class="hljs-selector-tag">nav</span> {
  <span class="hljs-attribute">display</span>: block;
}
</code></pre>

<p>This makes the new semantic elements behave like <code>&lt;div&gt;</code>
elements (which are <a href="/html-and-css/css-box-model/#block-elements-and-inline-elements">block boxes</a>, not inline boxes) in legacy browsers.</p>

</div></div>


<div class="content"><div class="content__wrapper">

<div class="subheading"><h2 class="subheading__heading" id="summary"><span style="background-color: rgb(249, 250, 251); box-shadow: rgb(249, 250, 251) 11px 0px 0px, rgb(249, 250, 251) -13px 0px 0px;">Summary</span></h2></div>

<p>Defining graphical styles with CSS is how we convey the structure of a web
page to humans. By marking it up with <code>&lt;header&gt;</code>,
<code>&lt;article&gt;</code>, <code>&lt;figure&gt;</code>, and other HTML
sectioning elements, we’re able to represent those visual styles to machines,
as well.</p>


<img src="https://internetingishard.com/html-and-css/semantic-html/semantic-html-ffab7c.png">

<p>To understand why this is important, we really have to empathize with the
machines reading our content. Before semantic HTML was a thing, developers used
a bunch of <code>&lt;div&gt;</code>’s with different and somewhat arbitrary
class names to define the structure of their pages. For example, all of the
following elements are logical names for a site-wide header:</p>

<pre class="highlight"><code><span class="hljs-tag">&lt;<span class="hljs-name">div</span> <span class="hljs-attr">class</span>=<span class="hljs-string">'main-menu'</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">div</span> <span class="hljs-attr">class</span>=<span class="hljs-string">'top-nav'</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">div</span> <span class="hljs-attr">class</span>=<span class="hljs-string">'top-banner'</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">div</span> <span class="hljs-attr">class</span>=<span class="hljs-string">'header'</span>&gt;</span>
</code></pre>

<p>Machine readers used to have to make sense of all the above
<code>&lt;div&gt;</code>’s and more. The new semantic HTML elements we
learned in this chapter are like standardized versions of these class names.
Now, they can simply look for a <code>&lt;header&gt;</code> element. We can
still add whatever class name we want to it for styling purposes, but search
engines and screen readers now have a predictable way to identify headers
across every HTML5 website on the Internet.</p>

<p>The semantic elements we covered in this chapter are best practices for
modern websites, but keep in mind that they hardly scratch the surface when it
comes to extra meaning you can add to your web pages. Just for starters:</p>

<ul>
  <li><a href="http://schema.org/docs/gs.html" target="_blank">Schema.org
  microdata</a> lets you alter the appearance of your site in search engine
results.</li>

  <li><a href="https://dev.twitter.com/cards/getting-started" target="_blank">Twitter cards</a> define how your web page is displayed
    in tweets.</li>

  <li><a href="https://developers.facebook.com/docs/sharing/webmasters#markup" target="_blank">Open Graph metadata</a> changes how 
Facebook shares your content.</li>

</ul>

<p class="nudge-desktop--smaller">This kind of stuff is closer to the realm of
technical SEO, so we’ll leave you to explore it on your own. In the next
chapter, we’ll switch gears again and introduce another critical component of
websites (especially e-commerce ones): forms.</p>


</div>