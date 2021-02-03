---
title: An Ode to Slim

date: 2021-02-02
---

My framework of choice for building PHP web applications is [Slim](https://slimframework.com). It's small and unobtrusive, staying out of my way and letting me structure the application however I want. When I do run up against it, it adheres to a bunch of [PHP Standards Recommendations](https://www.php-fig.org/psr/) (PSR), specifically [PSR-7](https://www.php-fig.org/psr/psr-7/) and [PSR-15](https://www.php-fig.org/psr/psr-15/). These PSRs stipulate that HTTP requests (how your app communicates with the world) comply with the revelant HTTP RFCs. This has forced me to re-architect my applications in ways that are consistent across the board, and has resulted in cleaner code.

At its core, Slim utilizes [nikic/fast-route](https://github.com/nikic/FastRoute) to handle incoming requests and dispatch the relevant controllers. While this was my biggest hurdle to adopting Slim a few years ago, I can't imagine writing an application without it now. As with PSR-7/PSR-15, adapting to working with Slim and FastRoute has helped me mature as a developer. Plus, I get pretty URLs out of it. What's not to love?

Protip: There's a few ways to resolve your controllers. Use an [invokable class](https://www.slimframework.com/docs/v4/objects/routing.html#using-an-invokable-class), it's the best method.

While I'm on the topic of writing better code, I should also give a shoutout to [PHP-DI](https://php-di.org/), my dependency injection container of choice. I'll be hoenst with you: I straight up don't understand dependency injection on a conceptual level. Fortunately PHP-DI's documentation and community examples are top-notch, and I've managed to bash a semi-functional dependency container together. It also helps that PHP-DI has an [entire section of documentation](https://php-di.org/doc/frameworks/slim.html) for working with Slim.

[EasyDB](https://github.com/paragonie/easydb) from Paragon Initiative Enterprises is hands-down the best way to talk to a database without adding layers of complexity. I know I should probably be using an [ORM](https://en.wikipedia.org/wiki/Object%E2%80%93relational_mapping) (and let's be honest, I'm close to making that jump), but I just really like writing SQL by hand. PIE is _the_ world leader in secure PHP code, and EasyDB really shines here. [PDO](https://phptherightway.com/#pdo_extension) is already a secure choice, and EasyDB's thoughtful additions add a ton of easy-to-use funcionality to that foundation.

As far as template engines go, nothing, and I mean nothing, holds a candle to [Twig](https://twig.symfony.com/doc/3.x/). I have never experimented with another PHP templating engine because there's never been a reason to do so. Twig has everything I could ever want, and so much more. The template syntax is easy to use and simultaneously incredibly powerful. I mean, check this out:

> You can also provide a list of templates that are checked for existence before inclusion. The first template that exists will be included:  
> `{% include ['page_detailed.html', 'page.html'] %}`

Native PHP can't even do this! How cool is that?

I also need to give a shoutout to [odan/slim4-skeleton](https://github.com/odan/slim4-skeleton) by [@dopitz](https://twitter.com/dopitz). Seeing how this application is built has been instrumental in helping me work around some of the more esoteric design concepts I've struggled with. Seeing [Action Domain Responder](https://github.com/pmjones/adr/blob/master/ADR.md) contextualized in Slim inspired me to tackle some new projects with a fresh approach. I owe [@dopitz](https://twitter.com/dopitz) a huge debt of gratitude.

Slim and its ecosystem are a wonderful middleground between writing too much of an application on your own (and running into [NIH](https://en.wikipedia.org/wiki/Not_invented_here)), and letting the framework dictate your entire stack. If you're an aspiring programmer, or well on your way to becoming an experienced developer, give Slim a shot.
