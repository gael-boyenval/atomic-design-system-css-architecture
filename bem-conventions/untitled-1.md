# Files names and block names

{% hint style="success" %}
**Files names should use the the same firsts words of the block name**
{% endhint %}

this allow us to find the related css file just by looking at a piece of markup. 

exemple : 

```markup
<!--...-->
<form class="go-login">
<!--...-->
```

```text
organisms/_o.login.scss
```

```css
.go-login {
    /*...*/
}
```



{% hint style="success" %}
you can create **families** of blocks by referring to the **first word of the block names** in a filename
{% endhint %}

it is mostly useful for related atoms or utilities that you want to keep in a same file :

note that for families, the file-name is plural and the first word of the block family is singular

```text
atoms/_a.headings.scss
```

```css
.ga-heading {
    /*... no styles here, because it's not modifiers, just a block family */
    &-large {
        /* heading-large styles */
    }
    
    &-medium {
        /* heading-medium styles */
    }
}
```

note the notation, we don't use a modifier delimiter \(`.ga-heading--large` but `.ga-heading-large` with one dash \)

{% hint style="success" %}
**Keep related usage files together by using the same first word**
{% endhint %}

```text
├── atoms/
│   ├── ...
│   ├── _a.input-field.scss
│   ├── _a.input-switch.scss
│   ├── _a.input-checkbox.scss
│   ├── _a.input-radio.scss
│   └── ...
```

