# Notes on Never Graduate Week 2020

Each year the alums of The Recurse Center gather for a week. It's called "Never Graduate Week" because we never graduate -- we're all still part of the community even after our batch is over. This year we're gathering online because of COVID-19.

I'll be keeping notes here, inspired by [Ashley Blewer](https://twitter.com/ablwr/status/1259842898922819584?s=20).

## Goals for the week
I want to spend some time outside of Javascript. To bend my mind towards concepts that don't exist in JS. Or, I should probably say, are not clearly expressed in JS. Concurrency, perhaps. Memory issues, maybe. What is it like to work with a compiled language? 

Towards that end I plan to learn a bit of Rust. Make a simple game. Make a simple CLI.

I also want to leave space for the serendipitous crossing of paths with other Recursers. And I want to make sure to take good care of my body. Drink water! Go outside!

## Monday May 11
- Started doing [Rustlings](https://github.com/rust-lang/rustlings/), an exercise-based approach to learning Rust. Most of this feels like a direct translation of Javascript, but I ran into a few things that just seem odd. Which is exciting! The point of learning Rust is to escape from my JS-centric mindset. It's happening already!
- Looked at Amethyst, a game framework for Rust. 
- Watched [a video on Game development in Rust](https://www.youtube.com/watch?v=aKLntZcp27M) by Catherine West. She explains why you might want to use an Entity Component System. ECS is [the design principle behind Amethyst](https://book.amethyst.rs/stable/concepts/entity_and_component.html) (and many other game engines).
- Signed on to the Rust Discord. Chatted a bit. Folks were very responsive! I'm liking the Rust community. It seems they put a lot of effort into making it welcoming for newbies.

## Tuesday May 12
- What is a "named lifetime"?
  - See the docs on [Lifetime Annotation Syntax](https://doc.rust-lang.org/book/ch10-03-lifetime-syntax.html?highlight=named,lifetime#lifetime-annotation-syntax).
  - I don't really get this. The compiler needs to know how long to keep a reference around, but how do I know when to tell the compiler? For now, I'm just going to monkey my way along. Here's the basic syntax:
  ```
  &i32        // a reference
  &'a i32     // a reference with an explicit lifetime
  &'a mut i32 // a mutable reference with an explicit lifetime
  ```
- What is the difference between `str` and `&str`?
  - See the docs on [dynamically sized types](https://doc.rust-lang.org/book/ch19-04-advanced-types.html#dynamically-sized-types-and-the-sized-trait)

