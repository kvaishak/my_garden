---
title: Technical Debt
---

Technical Debt is a metaphor coined by a Software programmer - **Ward Cunningham**.

What he meant by the term debt was that - when we borrow money from someone we are granted with that sudden purchasing power, but until you pay back the entire amount you are going to continue to pay the interest for something which is not completely owned by you.

Similarly, rushing software out the door seems like a good idea, but eventually, you would have to go back and repay that loan by refactoring the program to reflect your knowledge of the program as you acquire it.

> “If you develop a program for a long period of time by only adding features but never reorganising it to reflect your understanding of those features, then eventually that program simply does not contain any understanding and all efforts to work on it take longer and longer.”— **Ward Cunningham**

This does not mean that **accumulating debt** by writing code to reflect your current understanding of your problem, even if that understanding is partial is a bad idea. Nor does it imply the idea of doing code poorly with the intention of doing a good job later.

Software development is a constantly evolving process. Requirements change, feed back from users might result in scraping of perfectly working code, bugs and issues arise, fixing of those bugs might spawn further un-intensional bugs, changes in third party package dependency might lead to breaking of the applications etc. Hence there is no way to ship perfect code every-time and we have to work with our current understanding of the problem and make sure our code reflects your understanding as best as we can.

But there comes a time during the evolution of the product when it becomes hard to bring in more features or functionality for the product without a major restructuring.

Without repaying this **debt** it becomes impossible for people to work effectively in what might feel like a collection of rush code, outdated core requirements that didn’t catch up with the evolving product and shortcuts and quick fixes done by people who no longer work there.

So rather than waiting for the bubble to burst, a good practice would be to occasionally take a step back from the usual feature/development cycle and look back on the ways through which the product has evolved over time and try to make sure that the code at that point of time best reflects your current understanding of what problem your product is trying to solve. Repaying this **debt** in such a short continuous manner can help us prevent the sporadic occurrence of “debt bubble” which can lead to stagnation and subsequent decline in product development for a long period of time.

---

#### Case study
