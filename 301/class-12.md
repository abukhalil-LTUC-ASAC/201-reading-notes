# Light Partial Reading

Continuing off from the previous EJS class, we will talk a bit more about partials. Your HTML function of sort, where you'd repeat whatever content you want over multiple pages and areas such as ***nav bars***.

## `views/partials` Your New Home

That nav bar partial would only contain the HTML needed to create it. such as: 

```
<!-- views/partials/navbar.ejs -->
    <div class="header clearfix">
        <nav>
            <ul class="nav nav-pills pull-right">
                <li role="presentation"><a href="/">Home</a></li>
            </ul>
            <h3 class="text-muted">Node.js Blog</h3>
        </nav>
    </div>
```

And so is for the footer, each in a separate `.ejs` files: 

```
  <!-- views/partials/footer.ejs -->
    <footer class="footer">
        <p>© 90210 Lawyer Stuff.</p>
    </footer>
```

These lines are then included in whenever by using `<%- include( PARTIAL_FILE ) %>`.

> [As you can see creating and including partials is very straightforward with EJS.](https://medium.com/@henslejoseph/ejs-partials-f6f102cb7433)