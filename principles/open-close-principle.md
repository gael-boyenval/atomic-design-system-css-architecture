# Open / Close Principle \(OCP\)

### Definition :

> _**"A class should be open to extension and closed to modification"**_

{% hint style="info" %}
In more "CSS friendly terms" this statement says that **classes should never be modified from a different place from where they are declared.** Instead we should use multiple classes to achieve to the desired behavior. 
{% endhint %}

Another statement we can make is : 

{% hint style="info" %}
**A component should never change based on where it is, but be extended so we can use as many variation as required to be used in various contexts**
{% endhint %}

### Let's have an exemple :

look at the following **bad exemple** of code :

```markup
<button class="button">Action Button</button>
<div class="context">
    <button class="button">Action Button</button>
</div>
```

```css
.button {
    /* ... button's styles */
    color: green;
}

.context {
    /* ... context's styles */
}

.context .button {
    color: blue;
    margin-left: 16px;
}
```

There is multiple mistakes here regarding either the **OCP** and the **SRP** \(open/close and single responsibility\) :

1. we modify the color of the button depending on his context. 
2. we modify the `.button` class by adding a property
3. we add to the button the responsibility of the margin

### To follow both the **OCP** and the [**SRP**](single-responsibility-principle.md)**,** we could have done :

```markup
<button class="button">Action Button</button>
<div class="context">
    <button class="
        context__action
        button button--blue
    ">
        Action Button
    </button>
</div>
```

```css
.button {
    /* ... button's styles */
    color: green;
}

.button--blue {
    color: green;
}

.context {
    /* ... context's styles */
}

.context__action {
    margin-left: 16px;
}
```

Note that in the previous exemple, we used the [**BEM**](../bem-conventions/bem-presentation.md) naming convention, more detailed informations about [**BEM**](../bem-conventions/bem-presentation.md) will follow. 

Now you can see that we extended the `.button` class with a `.button--blue` option, or more precisely a modifier \(to follow the BEM convention\).

this modifier allow us to use the blue variation anywhere we see fit in the code source. 

Secondly, instead of adding the margin directly to the `.button` trough an override, we created a class attached to the `.context` class called `.context__action` that is responsible for creating the required white space. 

In the real world, both `button` and `context` are being instantiated in different places \(even different files\)

This approach has multiple benefits. 

* By not modifying button at all from context, we keep the component decoupled from one another. Deleting the `button` css file will delete all instances of the `button` class of the code base
* We are not tied to structure \(using a `button` with `.context__action`, it could be for exemple, a link instead\)
* It's more flexible and safe, because for instance, if we need to add another `button` into `context`, we maybe don't want it to have a `margin-left` in this specific use-case 



