# Personnal website

Link : [tomboulier.github.io](tomboulier.github.io)

This is built using [GitHub Pages with Jekyll](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/setting-up-a-github-pages-site-with-jekyll) and the [minima template](https://github.com/jekyll/minima).

## How to build and test this website

First you need to [install Jekyll](https://jekyllrb.com/docs/installation/).

Then clone this repository:
```
git clone https://github.com/tomboulier/tomboulier.github.io
cd tomboulier.github.io
```

Finally, build and run the server with the following command:
```
bundle exec jekyll serve
```

You can now navigate locally into the website using the adress given by Jekyll (usually [http://127.0.0.1:4000/](http://127.0.0.1:4000/)).

## How to add a post

As explained in [Jekyll documentation](https://jekyllrb.com/docs/posts/), you simply have to create a `markdown` file in the `/_posts/` folder, with the following format:

```
YEAR-MONTH-DAY-title.md
```

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit
numbers, and `title` will be used as a title in the URL.

The markdown file must begin with a layout like so:

```markdown
---
layout: post
title:  "This is my title"
---

Example of a blog post.
```

but we can also add some more information such as:
```markdown
---
layout: post
title:  "Another example."
date:   2022-03-09
categories: data-science
---

Another blog post, in the "data science" category.
```

### How to add an image to a post

If you want to add an image which is located in `/assets/images/example.jpg`, simply write:

```
![image name](/assets/example.jpg)
```

### How to add a link to a file in a post

As mentionned in the [Jekyll documentation for links](https://jekyllrb.com/docs/liquid/tags/#links), if you want to add a link to an Excel file located in `/assets/files/example.xlsx`, the command is:
```
[Excel]({% link /asassets/files/example.xlsx %}) 
```