# BEM : presentation

## Block / Element / Modifier

### What is BEM ?

BEM was created by _**Yandex**_, the "Russian Google" in 2009.

It is a component based architecture and naming convention.  
It stand for _**Block / Element / Modifier**_. You may be familiar with this very well known namming convention. But it is also one of the most **misunderstood** yet the **most safe and advanced** methodology I had the pleasure to work with. 

{% hint style="info" %}
**I strongly encourage you to** [**read the docs**](https://en.bem.info/)\*\*\*\*
{% endhint %}

### Why BEM ? It's so ugly !

One of the most common critic for BEM is that it is ugly, and that **those long classes names are making the markup hard to read**. I completely understand and it is often the main reason why developer do not want to switch to **BEM**. It's very sad because **the true beauty of BEM is hidden**. And I make you a promise : used right, you will love it so much, that you will see it as the only option out there to writing good CSS.

#### What are we talking about ? 

When I talk about BEM, i'm refering to the class naming scheme. If you carefully [read the documentation](https://en.bem.info), BEM comes with practices [about file structure organization](https://en.bem.info/methodology/filestructure/). As we will use ITCSS, we should not feel concerned with the BEM file structure principles.

### The good stuffs about BEM

#### Just by looking at a piece of markup :

* you can know witch classes are related to others
* you can also know in witch file they are declared, reducing headache
* you can understand the role of the class \(And therefore better follow the SRP\)

**Following theses practices will help you:**

* make decision about emplacement easily
* get self documented code, and logically reduce the need for CSS documentation
* keep specificity low \(because most of your selectors will only be composed of one classe\)
* make class colision almost impossible \(all classes will be uniques\)
* thus, making it safer to have multiple sources of code \(any CSS frameworks mixed with your own\)

## How does it works ?

Please note that the following part was completely copy-pasted from the [documentation site](https://en.bem.info/methodology/key-concepts/)

### _Block features_

_**Nested structure**_

{% hint style="success" %}
_**Blocks can be nested inside any other blocks.**_
{% endhint %}

_For example, a `head` block can include a logo \(`logo`\), a search form \(`search`\), and an authorization block \(`auth`\)._

![Head block components](https://en.bem.info/kFetIbKxQdABHhUecbic45Il0Bg.png)

_**Arbitrary placement**_

{% hint style="success" %}
_**Blocks can be moved around on a page, moved between pages or projects.**_ 
{% endhint %}

_The implementation of blocks as independent entities makes it possible to change their position on the page and ensures their proper functioning and appearance._

_Thus, the logo and the authorization form can be swapped around without modifying the CSS or JavaScript code of the blocks._

![Altering the block positions](https://en.bem.info/v80tUiEPgSQtyW9a7C8rxdn-5EM.png)

![Altering the block positions](https://en.bem.info/0bbhZyhaBhRzqBh5nLYQEnFpDTk.png)

_**Re-use**_

{% hint style="success" %}
_**An interface can contain multiple instances of the same block.**_
{% endhint %}

![Online store products](https://en.bem.info/VBlEdksG7XkL4DLPWe4rcYb5hGo.png)

### _Element_

\_\_

A constituant of a block

{% hint style="danger" %}
_**An element can't be used outside of his block.**_
{% endhint %}

_For example, a menu item is not used outside of the context of a menu block, therefore it is an element._

![Menu items](https://en.bem.info/cPrdQL4EZZdhPIrcYOayygPBSm4.png)

### _Modifier_ <a id="modifier"></a>

_A BEM entity that defines the appearance and behavior of a block or an element._

_The use of modifiers is optional._

_Modifiers are similar in essence to HTML attributes. The same block looks different due to the use of a modifier._

_For instance, the appearance of the menu block \(`menu`\) may change depending on a modifier that is used on it._

![Add a menu to the footer](https://en.bem.info/WSU5nwZla7p44W2tdxiP371xx38.png)

_Modifiers can be changed in runtime \(for example, as a reaction to a DOM event of the block\), or via other blocks._

_For example, if the wrong credentials are entered when a user clicks the Sign In button \(the 'click' DOM event\), the 'visible' modifier is set on a hidden block with error messages._

{% hint style="warning" %}
We will see later that our version of BEM provide a better way to handle those types of changes
{% endhint %}

here the end of the copy-pasted content, and i'm not even a little ashamed…

### If you don't believe BEM is awesome

then you may want to believe them \(they are all gurus in the CSS world\) : 

**Harry Roberts** Consultant Front-end Architect  
"_I use BEM notation on everything I build now as its usefulness has proved itself over and over."_

**Mark McDonnell** Technical Lead, BBC News  
"_Itʼs less confusing than the other methods \(i.e. SMACSS\) but still provides us the good architecture we want \(i.e. OOCSS\) and with a recognisable terminology."_

**Connie Chan** Design Director, Thoughtbot  
"_Combined with a preprocessor, BEM makes keeping your CSS modular and object-oriented a breeze."_

**Jonathan Snook** Author of SMACSS, Xero  
"_Most common misspelling is “SMACCS”. I should just rename it to BEM."_

**Paul Irish** Front-end Developer, Google Inc.  
"_This BEM stuff is next-level shit. Itʼs incredible how methodical it is."_

**Necolas Gallagher** Software Engineer, Twitter  
"_BEM is far more than a HTML/CSS system. Iʼve got no plans to use it all; just adapted some of its ideas."_



{% hint style="info" %}
**I strongly encourage you to** [**read the docs**](https://en.bem.info/) **\(again...\)**
{% endhint %}

