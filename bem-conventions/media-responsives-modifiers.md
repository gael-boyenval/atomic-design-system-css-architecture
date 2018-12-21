# Media / responsives modifiers

{% hint style="success" %}
**When you want a class to apply to a specific media querie, instead of the '--' delimiter, use a '@' delimiter.**
{% endhint %}

Exemple :

```markup
<button class="
    ga-button
    ga-button--small
    ga-button--large@from-medium
    gu-hide@print
    ">
    button text
<button>
```

here we instantiated a class that tell us that the button will be a large one from medium screen and a utility telling us that the button should be hidden for print. 

in css, we need to escape the @ : 

```css
.ga-button {
    &--large {
        /* large option styles */    
    }
    
    @media screen and (min-width = 720px) {
        &--large\@from-medium {
            /* large option styles */    
        }
    }
}
```

```css
.gu-hide {
    @media screen and (max-width = 720px) {
        &\@to-medium {
            display: none !important;    
        }
    }

    @media screen and (min-width = 720px) {
        &\@from-medium {
            display: none !important;    
        }
    }
}
```

