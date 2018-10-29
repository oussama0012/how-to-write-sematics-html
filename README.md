# how-to-write-sematics-html
“Semantic HTML” refers to the idea that all your HTML markup should convey the underlying meaning of your content—not its appearance. We’ve already been writing semantic HTML (e.g., using <strong> instead of <b>), but there’s a whole set of elements designed for the sole purpose of adding more meaning to the overall layout of a web page. They’re called “sectioning elements”, and they look something like this:
    <img src="https://internetingishard.com/html-and-css/semantic-html/html-sectioning-elements-00c3fd.png" alt="sematics-html">
Using these as an alternative to <div> elements is an important aspect of modern web development because it makes it easier for search engines, screen readers, and other machines to identify the different parts of your website. It also helps you as a developer keep your site organized, which, in turn, makes it easier to maintain.
    <img src="https://internetingishard.com/html-and-css/semantic-html/semantic-html-ffab7c.png" alt="sematics-html">
We’re going back to straight HTML this chapter—no box model, flexbox, or positioning schemes. However, that’s not to say you can’t apply all of the CSS rules from previous chapters to these new elements. Think of sectioning elements as div’s, but with meaning.
    
    <hr>
    
                           <h1>setup</h1>
    
   
   <hr>
    
Our example for this chapter will be a simple unstyled HTML document. Create a new Atom project called semantic-html with a new file in it called article.html. Add the following:

<!DOCTYPE html>
<html lang='en'>
  <head>
    <meta charset='UTF-8'/>
    <title>Semantic HTML</title>
  </head>
  <body>
    <h1>Interneting Is Easy!</h1>
    <ul>
      <li><a href='#'>Home</a></li>
      <li><a href='#'>About</a></li>
      <li><a href='#'>Blog</a></li>
      <li><a href='#'>Sign Up</a></li>
    </ul>
  </body>
</html>



That h1 and ul are presumably the top-level banner for our website—not the main content of the web page. We’ve never had to make this distinction before, but that’s what this whole chapter is about.
