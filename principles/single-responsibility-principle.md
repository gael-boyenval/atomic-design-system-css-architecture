# Single Responsibility Principle \(SRP\)

### Definition : 

> A class should have only one responsibility.

{% hint style="info" %}
“_Loosely, the single responsibility principle states that **every module or chunk of code\(...\) should do one job well and one job only**. The benefits of this are mainly in the way of maintainability and extensibility.“_
{% endhint %}

### Let's take an exemple that does not follow the SRP :

```css
/* <a href="/product" class="promo">Buy now!</a> */

.promo {
    display: block;
    padding: 20px;
    margin-bottom: 20px;
    background-color: #09f;
    color: #fff;
    text-shadow: 0 0 1px rgba(0,0,0,0.25);
    border-radius: 4px;
}
```

_"Here we have a class for a promotional box of content. Here we are doing **two** things—we are defining box model and structure and we are defining cosmetics \(colouring etc\)._

_We can refactor this code to adhere to the SRP by splitting those two chunks of functionality into two classes:_

```css
/* <a href="product" class="island  promo">Buy now!</a> */


.island {
    display: block;
    padding: 20px;
    margin-bottom: 20px;
}

.promo {
    background-color: #09f;
    color: #fff;
    text-shadow: 0 0 1px rgba(0,0,0,0.25);
    border-radius: 4px;
}
```

\_\_

_We now have two classes which each carry a single responsibility; `.island` boxes off content and `.promo` applies our promotional styling. This now means that we can do things like this, which previously we couldn’t:_

_Previously we couldn’t have managed this as the `.promo` class also carried a lot of box model; by abstracting our code into single responsibilities we can pick and choose what we want to use and where a lot more easily."_

{% hint style="info" %}
**All the** _**Previous**_ **exemples and contents are from** [**this great article**](https://csswizardry.com/2012/04/the-single-responsibility-principle-applied-to-css/) **by Harry Roberts, that I encourage you to read in full.**
{% endhint %}

