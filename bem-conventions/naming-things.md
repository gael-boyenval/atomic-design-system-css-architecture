# Naming things

## Don't be lazy, be explicit, be thoughtful

You should find names \(if there is not already\) for your classes that are explicit and well thought.  
**Once a name is used it is very hard to change it.**

### **Some general rules**

{% hint style="success" %}
#### **Work in collaboration with others**
{% endhint %}

Please do this in collaboration with designers and other BU's, especially if you don't speak english with ease.

{% hint style="success" %}
#### **Be as generic as the element you try to name**
{% endhint %}

Think of the position of the elemnt in the ITCSS pyramid, and try to find a name that match its genericness \(? I don't know the word\). let me clarify : for an organism you have an element that is very hight level and have a clear purpose in your interface, maybe a feature.

You should have a very specific name for it. 

In the other hand, a very generic element **should not have a name that mirror usage**, but a more  **functional, descriptive name about is nature**. 

For exemple, for the identification form of your app, you can call it `.go-login-form`, but imagine an icon that represent a `cog`, you should **not call it** `.ga-icon--parameter` _****_since **it ties the usage of the cog icon with the parameters** feature. Use instead `.ga-icon--cog`



{% hint style="danger" %}
#### **Do not use positions, sizes, or other components names in the name of your components**
{% endhint %}

For exemple, `.cm-sidebar-menu` or `.ca-alf-size-image` are not good names because they create a location or context dependency. We should create reusable, context agnostic components. **If a pattern is semantically tied to another one, or to a position, it may signify that you only need one component.**  


{% hint style="danger" %}
#### **Don't use abbreviation for components classes names**
{% endhint %}

Use only plain words to compose your classes names, this is also true for variables, mixins etc :

```markup
<div class="gm-horizontal-slider"></div>
```

and **not**

```markup
<div class="gm-horiz-sldr"></div>
```



{% hint style="warning" %}
You can use abbreviations in utility classes or some common Layouts, and for common sizes names. **But you need to make sure that everybody is on the same page.** 
{% endhint %}

**Exemple :**

```markup
<div class="
    gl-grid__column
    gl-grid__column--full
    gl-grid__column--1of2@from-medium-screen" >
    <span class="
        gu-margin-bottom--small
        gu-margin-bottom--large@from-medium-screen
        gu-margin-top--large
        gu-margin-bottom--extra-large@from-medium-screen">
        Hello
    </span>
</div>
```

This would be a bit overkill. We will prefer : 

```markup
<div class="gl-grid__col gl-grid__col--full gl-grid__col--1of2@from-md" >
    <span class="gu-mb--s gu-mb--l@from-md gu-mt--l gu-mt--xl@from-md">
        Hello
    </span>
</div>
```

**It is a bit cryptic,** but since those utilities should be used often and in a lot of places, peoples will learn quickly to read them.



\*\*\*\*

