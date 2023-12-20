# 

---

# Add New Profile to Sidebar

---

**View**
![](docx_img/1.png)

**Step 1: Modify `_config.yml` file**

```yml
# Site Author
author:
  name             : "Md. Imrul Hasan"
  avatar           : "profile.png"
  ...
  ...
  mastodon         : "imrulhasan"
```

> Add `mastodon` and assign value

**Step 2: Modify `_includes\author-profile.html` file**

```html
<div itemscope itemtype="http://schema.org/Person">

  <div class="author__avatar">
    ...
  </div>

  <div class="author__content">
    ...
  </div>

  <div class="author__urls-wrapper">
    <button class="btn btn--inverse">Contact</button>
    <ul class="author__urls social-icons">
        ...
        ...
        ...
        {% if author.mastodon %}
            <li><a href="https://mastodon.social/@{{ author.mastodon }}"><i class="fab fa-fw fa-mastodon" aria-hidden="true"></i> Mastodon</a></li>
        {% endif %}
    </ul>
  </div>
</div>
```

> Add new condition `{% if author.mastodon %}`

**Step 3: Add new styles `_sass\_utilities.scss` file using variable**

```scss
.social-icons {
    /* remaining css variables */
    .fa-mastodon {
        color: $mastodon-color;
    }
    /* remaining css variables */
}
```

**Step 4: Add value of the variable in Step 3 in `_sass\_variables.scss` file**

```scss
$mastodon-color  : #6364ff;
```

- [Ref](https://github.com/academicpages/academicpages.github.io/commit/0ff8195d4d91963c8b4ed9e3a0aeb14c09bce1b5)

---









