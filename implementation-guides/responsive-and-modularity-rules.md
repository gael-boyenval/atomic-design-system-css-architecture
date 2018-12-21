# Responsive and modularity rules

### Modularity rules

In general terms, **float, margins, positions, top, bottom** \(...etc\) **properties are context based**. In order to be as reusable and modular as possible**, blocks entities should not set those properties**. That responsibility should fall to **layout and utilities classes or to the containing element entity** of another components. 

#### Sizes rules :

{% hint style="danger" %}
Components block level entities should not set sizes other than a **fixed one** \(14px\), or **100% / fluid**.
{% endhint %}

```css
/* DON'T */
.gm-block {
    width: 25%;
    /* 
    * 25% of what ? we should not be aware
    * of our context in order to be reusable
    */
}
```

```css
/* DO, when it make sense */
.ga-icon {
    width: 16px;
    /* some blocks require fixed sizes */
}
```

```css
/* DO */
.ga-button {
    display: inline-block /* or inline, or inline-flex */;
    /* natural content's size */
    
    &--full {
        /* a modifier to set it to 100% */
        width: 100%;
    }
}
```

```css
/* DO */
.ga-block {
   display: block;
   /* or */
   width: 100%;
   /* the context size will define the size of this element */
}
```



{% hint style="success" %}
You can use elements entities to define sizes, margins, or context of lower levels components
{% endhint %}

```css
.gm-search-bar {
    /* own search bar styles */
    padding: /*...*/;
    background: /*...*/;
    
    &__column {
        /* 
        * this will be used as emplacement 
        * for a lower level component
        */
        width: 33%;
        float: left;
        margin: 5px 8px;
    }
}
```

```css
.ga-input-search {
    display: block; /* or width: 100% if required */
}
```

```markup
<form class="gm-search-bar">
    <div class="gm-search-bar__column">
        <!-- the container constrain the input size -->
        <input type="search" class="ga-input-search" ...>
    </div>
    <div class="gm-search-bar__column">
        <!-- the container constrain the input size -->
        <select options="..." class="ga-input-select" ...>
    </div>
    <button 
        type="submit" 
        class="gm-search-bar__column ga-button ga-button--green">
        <!-- 
            you can use the gm-search-bar__column 
            element class directly on the block
            if you don't want to use a container div
        -->
        text
    </button>
</form>
```

#### 

#### Positioning rules :

{% hint style="danger" %}
**Components block entities should not use positions values other than relative**. Use instead Layouts, Utilities or higher level component elements to set positions
{% endhint %}

For the same reason as above. Relative positions are allowed since they are used to set a context for children elements that may have absolute or fixed position. 

{% hint style="danger" %}
**Components block entities should not use top, right, left, bottom properties**. Use instead Layouts, Utilities or higher level component elements to set positions
{% endhint %}



