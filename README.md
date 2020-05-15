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
  
- Tried out the Amethyst 2D Starter. It failed on an error I don't understand. It seems to be a platform compatibility issue 🤷🏻‍♀️? I opened [an issue](https://github.com/amethyst/amethyst-starter-2d/issues/18). It seems that others have had similar issues recently, so I hope my issue is more helpful than annoying.

- Trying out Conrod, a UI library for Rust. 
  - Hit an issue running the examples, but figured it out pretty quickly (thanks to nice error messages!). Reported the issue [here](https://github.com/PistonDevelopers/conrod/issues/1345).
  - I played around with modifying the examples for a bit. Just doing trivial things like changing colors and font size. This is a pretty involved library, but the docs look nice. I think I'll return to this in a day or so, after I have a little more Rust under my fingers.

### Ownership in Rust
I encountered this sentence in the Rust Book: "Rust's central feature is ownership."

There are three ways to deal with memory:
1) Garbage collector - In Javascript this happens behind the scenes(?)
2) Manually - As in C
3) Ownership - Rust does this.

Question: What other languages use ownership? Is Rust totally unique? There must be some prior art, even if academic or obscure. Wondering...

Your data is on the STACK or the HEAP. In Rust, you have to think about this, because things behave differently depending. 

```
String literal        =/=       String type
--------------                  -----------
on the stack                    on the heap
cannot be mutatated             memory requested at runtime
memory allocation
  known at compile time
```

`drop` is called (by Rust) when memory goes out of scope.

"Double free error" --> BAD!
These are prevented by Rust `drop`ping data that no longer needs to be kept around. One of the reasons they say Rust is memory-safe.

The ampersand!
The `&` gives reference to the value without taking ownership. Now I have my answer to the question from the beginning of the day :)

Rust prevents data races. 
Mutation is allowed, but very closely controlled.
Only one thing gets to write to memory at once!

## Wednesday May 13
- Learning structs in Rust.
- The "update syntax" in Rust is just like the object spread operator in Javascript. Which is by far my favorite operator! ✨
- ```
        let newThing = Thing {
            name: String::from("So new, this thing!"),
            ..old_thing
        };
  ```
- Still don't get "named lifetimes".  
- A wonderful presentation on Web Standards!
- Went to a talk on [APL](https://tryapl.org/#), which I know nothing about. Wild stuff!
- Working through [creating a CLI in Rust](https://doc.rust-lang.org/book/ch12-00-an-io-project.html)
  - Types in Rust
    - "we very rarely need to annotate types in Rust"
  - the debug formatter: `:?`
  - "Using primitive values when a complex type would be more appropriate is an anti-pattern known as primitive obsession." Lol, never heard this before.
  - Contructors for custom types are cool!

## Thursday May 14
- Went to the beach! And didn't see a single computer all day. Biked there, to Reis Beach, laid out a blanket, ate some pasta, cuddled with my sweetie. It got cold once the wind whipped up and the sun went behind the clouds.

## Friday May 15
- Presentations!
  - Ashley Blewer	Throttled, network-based performance...art
  - Stephen Tu	Derivative free optimization
  
