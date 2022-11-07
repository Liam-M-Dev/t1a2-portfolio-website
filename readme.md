# General Documentation of project WIP

## Liam Massey  

***

## Links

[Github repo](https://github.com/Liam-M-Dev/t1a2-portfolio-website)

[Netlify live site](https://liam-m-t1a2.netlify.app/)
***

### Purpose

The purpose of my web developer portfolio is to design and implement a website portfolio that not only advertises myself and my brand to potential employers but also shows a strong message of my morals and who I am as a person. I wanted to show off what skills I had learnt during the initial boot camp by using html semantics and SCSS. Whilst still keeping it within the aesthetic that I like which is a cross between minimalism and brutalism design styles. Going forward I would like to expand on these ideas and further develop a strong skill set in web development and design.

### Target Audience

My target audience is mainly trying to appeal towards  
***

### Tech Stack

- HTML
- SCSS/CSS
- Wire frames - Figma
- Gimp -Image resizing/modelling
- Github - repo
- Netlify - live website deployment

***

### Functionality/Features

Utilizing various techniques I was able to bring some solid functionality/features that would make the site accessible and easy to navigate. These include  

- A navigation bar
- A footer with social links
- Color scheme that is clear and inclusive
- Page layout that is readable and easy to follow
- Logo that links back to home page
- Contact form  
- Clear imagery
- Link to my available resume
- Project cards that link to outside pages of projects.
- Blog cards that link to the blog posts

### HTML and SCSS

With HTML I have used semantic html to make the pages easier to read for developers and people with screen readers. For example within the about page I have utilized ```<section>```, ```<article>```, ```<figure>``` and presentational tags to communicate the content.

```html
<section class="about">
      <article class="about-text">
        <p>Hello! My name is Liam and I am currently studying at Coder Academy.</p>
        <p>I'm a creative person that enjoys problem solving.
          I have a diploma of horticulture with a variety of skills and life experience.  
          What interests me with web development is the process of translating an idea into a fully functional site.
          For a bit more info, <a href="../resume/liam-resume.pdf">here's my CV</a></p>
      </article>
      <figure class="about-image">
          <img src="../images/myself-patti.jpg" alt="Myself with my cat patti">
      </figure>
</section>
```

This was the first time I have used SCSS with coding and have found it incredibly helpful and enjoyable to learn. I found using different tools such as partial stylesheets, mixins and variables made it a lot easier to keep my code clean and understandable.  
I created different mixins for text and layout, although a lot of the text are repeated I found it good practice because if I wanted to change the font for a component I could just change that in the mixin section and it would apply to every text component that has that mixin. some examples of my scss are:  

```scss
@mixin sub-heading {
  font-weight: 300;
  font-family: 'Montserrat', sans-serif;
}

@mixin link-font {
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
}

@mixin paragraph {
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
}

$primary-color: #9a9a9a;

$container-color: #a2a2de6f;

$button-color: #a2a2de;

@mixin default-button {
  width: 10em;
    padding: 1em;
    margin-top: 20px;
    align-self: center;
    background-color: $button-color;
    font-size: 1em;
    border-radius: 5em;
    border: 2px solid $button-color;
}

```

Styling for my navbar was really interesting for me as it helped me understand nesting

```scss
.nav{
  display: flex;
  flex-flow: row nowrap;
  justify-content: center;
  align-items: flex-end;
  ul {
    display: flex;
    flex-flow: row nowrap;
    a{
      @include link-styles;
      li {
        margin-right: 5px;
        @include link-font;
      }
      &:hover {
          background-color: black;
          color: white;
          transition: 2s;
        }
    }
  }
}
```

For the project cards I wrapped an ```<a>``` around ```<article>``` and ```<div>``` containers so that I could set the background image as the project image using SCSS.  
**HTML** and **SCSS** of project cards.

```html
<a href="https://github.com/Liam-M-Dev/calculator"><article class="project-card">
        <div class="back p-img-a"></div>
        <div class="front">
          <h3>Calculator App</h3>
          <p>A calculator app I built using HTML/CSS/JS</p>
        </div>
</article></a>
```

```scss
.project-card {
  width: 10em;
  height: 250px;
  position: relative;
  margin: 0 auto;
  padding: 10px;
  border: 2px solid $primary-color;
  border-radius: 5px;
  box-shadow: 2px 4px 6px;
}

.back{
  position: absolute;
  background-size: 100%;
  object-fit: contain;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 1;
  border-radius: 5px;
}

.front{
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 35%;
  z-index: 2;
  background-color: black;
  color: white;
  border-radius: 5px;
  padding: 2px;
  h3 {
    @include headings;
    font-size: 1em;
  }
  p {
    @include paragraph;
    font-style: italic;
    font-size: 0.85em;
  }
}
```

The contact form was made using simple html and styling with some scss to make sure it was easy to read.

```html
<form action="./contact.html" method="post"        class="contact-form">
        <label for="name">Name:</label>
        <input type="text" name="name" id="">
        <label for="email">Email:</label>
        <input type="email" name="email" id="">
        <label for="message">Leave a message:</label>
        <textarea name="message" id="" rows="4" cols="50">Please leave a short message</textarea>
        <button type="submit">Send Message</button>
</form>
```

```scss
form {
  @include flex-col;
  max-width: 22em;
  margin-left: 5px;
  background-color: $container-color;
  padding: 1em;
  label[for=name], label[for=email], label[for=message] {
    @include form-titles;
    font-size: 1.3em;
  }
  input[type=text], input[type=email] {
    padding: 10px;
    margin-bottom: 5px;
    border-radius: 1em;
    border: 2px solid $primary-color;
    font-size: 1em;
  }
  textarea[name=message] {
    margin-top: 5px;
    border-radius: 1em;
    border: 2px solid $primary-color;
    padding: 2px;
    font-family: 'Montserrat', sans-serif;
    font-size: 1em;
  }
  button {
    @include default-button
  }
}
```

***

### Sitemap

![Sitemap of portfolio](./docs/Sitemap.png)

***

### Screenshots
