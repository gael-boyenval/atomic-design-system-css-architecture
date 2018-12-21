# Introduction

This document is primarily intended to the **Garden design system contributors team**, but anybody can read and take what they want from it. At core this documentation is meant to provide clear and complete guidelines to create a **scalable, modular and safe CSS architecture in a context of various technical environments, legacy code base and cultural background.** 

To be more precise, our users are multiple business units of the same company, witch are fully independent and free in terms of technical, and design choices for their product. Some use React and CSS modules, others PHP based frameworks with huge less code bases. Some are creating from a blank slate, while other have to manage. 

It's why we needed an **optionable, collisison free, highly modular CSS** library that can be implemented pieces by pieces while playing well with legacy code bases.

### Preprocessor technical choice :

We choosed to use **SCSS** in combination with **POSTCSS.   
SCSS** for the general syntax and **POSTCSS** for his plugin ecosystem.   
We could have gone with **POSTCSS** alone, but we wanted a **well known, documented, stable syntax**, and the plugin based paradigm of **POSTCSS** may have forced us to write extensive documentation and thus create a steep learning curve about basic syntax alone.

I hope this documentation will be useful and comprehensive, but if you have any suggestion or question, do not hesitate to contact me.

Please keep in mind that I'm not a native english speaker, and that any suggestion, or correction about spelling, grammar or vocabulary will be highly appreciated.

### Special thank's to Harry Roberts work

You will see that a lot of stuff that are in this documentation come from [**Harry ROBERTS**](https://csswizardry.com) **\(aka csswizardry\)** mind.   
  
If you don't know him, I strongly encourage you to read and follow him. He is, in my opinion, **the CSS GURU you need to read the most**. He quite recently turned away from CSS to dive into the subject of web performance, but you can still find his older articles from his blog and find a lot of similarities with the content here. 





