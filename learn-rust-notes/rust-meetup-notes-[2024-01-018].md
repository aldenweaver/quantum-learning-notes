# Rust Meetup 2024-01-018 [Notes]

## Seattle Rust User Group
2024.01 Meeting (January 18, 2024)

## Important Dates
+ Rust meetups: Third Thursdays
+ Linux North America OSS conf: 4-16 through 4-18 at Seattle Convention center
  + Pop-up is a one-off event
+ Brussels conference

## About Rust
[Rust Language Website](https://www.rust-lang.org/)
+ Installation via Mac Terminal: `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
+ Cargo: the Rust build tool and package manager
+ Rust for crypto & blockchain

## Hardware
+ Candidate boards
+ Raspberry Pi Pico: system on a chip
  + About $20
  + Also knockoffs for around $6 (weACT is a brand)
  + Choices!
+ 2-core 32-bit multiple megaHZ
+ Board complexity
+ Busses & spy busses

## Embedded Systems Programming 
+ Choosing to program on Raspberry Pi 240
+ Different plugs cause different actions
+ White bread board surrounding circuit board
  + Hundreds of tiny wires from the actual CPU & small silicone wafer to a bigger size that is interfaced to the small inside world via small wires
  + Exposes a few dozen wires in the CPU to the end user
  + Software writes a 1 and electricity flows
  + No Operating System, nothing to load your program for you since there is no hard drive to load it from
  + Therefore, it does not load, it does something else
  + Instead of OS knowing to start with `main` function, it does not have that knowledge; a lot of what we take for granted is thus not there (?!)
  + No OS means no dynamic memory allocation
    + "No heap"
    + Memory managed language has heap
    + Write you allocator knowing you don't have a heap
    + No two programs can use the same memory at the same time (? -> challenge this assumption)
    + Dynamically make decisions such as how much data to hold via dynamic memory allocation
    + Security issues if you "trust" the data & data structure, which can allow your system to be exploited
    + Beginnings of writing a kernel
  + Linux -> Minix
  + [Minix](https://git.minix3.org/index.cgi)
  + Grabbing something off the shelf can hurt or help you; weigh the trade offs - paraphasing Brad G.
  + "They have no power to hurt you or to help you so who do you call on?" - paraphrasing
  + Function calls; prebuilt libraries & systems
  + Qubits

## Modes of Transport 
+ What bus are you using?
    + CAN bus
      + High-speed is a mega-bit
    + Transportation (data, cars, etc)
      + Modulate where motor is going by measuring wheel position
      + ECU in vehicle cannot be updated over the air
      + Queues (RabbitMQ)
+ Quantum transportation
+ 6G, Bell Labs 
  + Data transportation over air
  + Superfast processors, mega- & giga-hertz
  + What is the default clock speed of a Raspberry Pi Pico? 125 MHz
    + Bandwidth limitations & what causes them
    + [Raspberry Pi Pico SDK](https://www.raspberrypi.com/documentation/pico-sdk/)
    + "The Raspberry Pi Pico runs at 125 MHz by default. The clock divider allows us to run each state machine at a frequency between about 2 kHz and 133 MHz (assuming the system clock is 133 MHz)." - [forum link](https://www.digikey.com/en/maker/projects/raspberry-pi-pico-and-rp2040-micropython-part-3-pio/3079f9f9522743d09bb65997642e0831#:~:text=The%20Raspberry%20Pi%20Pico%20runs,system%20clock%20is%20133%20MHz).
    + Audio, mixing & matching
+ 4 zones for sending electricity data over the wires: 
  + Every hole under the plus gives power
  + Minus gives ground
  + Same ground, same power
  + (4 motors?) in cars
  + Rows & columns
  + A-B represent one electrical bar
  + Surgical power in one hole affects others in that row & column
  + Power surges
  + `Hello World` for embedded systems is turning on an LED light
  + GP I/O pin: general purpose I/O pin
  + External wires connect the holes & allow data to be trandferred
    + Similar to sonic modulators like an ARP synth modulator
    + No resistance with power flowing from above to ground damages the circuit (short circuit)
    + Not a far stretch to go from lighting a light to turning a motor, etc
    + Daily Bread Board
  + Question of the day: who is interested, & thus, how many resources are required? Approximations of resources
  + Ports: LED, KEY, GP
    + Port number to control mapping may vary based on hardware implementation (i.e., Raspberry Pi vs. WeACT hardware)
    + How to program regardless of variances/variations/varying variables?
+ REMEMBER WE ARE LIVING IN A GOLDEN AGE
  + How to properly leverage resources
  + The word of last season "Oct - Dec 2023" was patterns
  + The word of this season "Jan - March 2024" is resources
  + ["Quantum Computing: A Gentle Introduction"](https://s3.amazonaws.com/arena-attachments/1000401/c8d3f8742d163b7ffd6ae3e4e4e07bf3.pdf)
    + Can you quantify gentleness? -> Power of Love
    + How to quantify the unquantifiable?
  + Linear Algebra: matrix, matricies
  + Shor's algorithm
  + Mathematical constructs; break?
  + Learn rules to break them properly
  + Computer vision

## "Object Soup is Made of Indexes" Presentation by Jack O'Connor
[Object Soup is Made of Indexes Paper](https://jacko.io/object_soup.html)
+ Example: Games, when/where do monsters spawn?
  + Theology
+ Use lists & indexes to make this work
+ Rust structures (struct), implementations (impl), & functions (fn)
+ Moving semantics
+ Does it compile?
+ Core issue: creating & modeling graphs of objects for different uses (games, finance)
+ Relations (i.e., friends) make graphs, pointers
+ Rust playground making error noise? -> quantum error mitigation

From [referenced paper](https://jacko.io/object_soup.html):
`Part One: Move Semantics
A naive Rust translation doesn't compile:

struct Person {
    name: String,
    friends: Vec<Person>,
}

impl Person {
    fn new(name: &str) -> Person {
        Person { name: name.into(), friends: Vec::new() }
    }

    fn add_friend(&mut self, other: Person) {
        self.friends.push(other);
    }
}

fn main() {
    let mut alice = Person::new("Alice");
    let mut bob = Person::new("Bob");
    alice.add_friend(bob);
    bob.add_friend(alice); // error: borrow of moved value: `bob`
}
`

"Trigger infitine recurision & panic" -> trigger infinite recursion & "DON'T PANIC" as per Douglas Adams

+ Value moving
+ Parameters/input required for moving/transportation
+ Copying & cloning; calling clones
  + #[derive(Clone)]
+ Copying affects versioning (repositories)
+ Pointer/reference as a potential solution, but that does not work here
+ "Where's my money?" -> Where & WHEN
  + Blockchain, crypto
  + 
+ `&` symbol indicates a shared reference
+ Error message: "cannot borrow `bob` as mutable because it is also borrowed as immutable"
+ Mutability -> mute -> noise -> mutations
+ Mutuable reference (&mut) does not work either
+ In theory, there is no alias once you construct the graph
+ 99% unsolvable?
+ [Rust Docs on References & Borrowing](https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html)
+ How to mutate something borrowed? Interior mutability
+ Rc: reference counting
+ RefCell
  + Quantum cellular mutation
+ How to alias mutability?
+ so-called magic is explainable through mechanics, machinery, & science
+ Why does de-ref happen automatically?
+ Just because something compiles, doesn't mean it works
  + Run Miri (mirror!) to run code with extra checks; it is technicallly an interpreter and looks for underfined behavior if you break the rules!
  + "leak", "forget"; memory leaks; cycle collectors
  + Circular references; reference each other but nothing external references them
  + Cycle collectors clean up cycles
  + Weak pointers; solutions to fix 
    + A weak reference is a reference that does not keep what it is referencing alive solves the memory leak
    + Works more well with trees; different data structures
    + Harder to work with graphs
    + Which object references are weak vs. strong
    + Solving problems vs. solving problems in a scalable way
    + Break the cycle by clearing the collectors?!
    + When to break the cycle when things get more complex? Sustainability & scalability
    + RefCell has a rule that has a flag on the inside that if you try to mutate from two different locations, it crashes the program
      + Happens more often on complex programs
      + False conditions
      + Error message: `thread main panicked`
      + RefCell panicks where borrow checker rules are violated, so it is a predictable panic
      + Quantum error mitigation
      + Graph & cycles problem
      + Orbits follow cycles
      + Astronomy on a quantum scale -> geometry -> physics
      + References to the whole world
      + Using indexes for people objects (people struct implementations)
      + Deletion does not work with Vectors because objects are moving so location of pointer references change; requires HashMaps
    + A lot of things we have to do to make Rust compile, other languages & programmers are doing anyway
    + Useful & interesting applications across many fields
    + Naming, deletion, & versioning

## Modular Music Composer by Doug Stoeckmann
  + RedACT composer repository URL: https://github.com/dousto/redact-composer
    + [redact-composer](https://docs.rs/redact-composer/latest/redact_composer/)
    + [redact-composer-musical](https://docs.rs/crate/redact-composer-musical/latest/source/)
  + [release-plz](https://release-plz.ieni.dev/)
  + Manages releasing Rust crates via Git -> versioning
  + Modular composition
  + Documentation is crucial
  + "Update Element link to point to trait instead of macro"
  + RedACT Composer
  + Pull request checks & merging
  + Pull request tells you about the changes that were made
  + Make sure what was changed was accurate
  + Different crates have different changes
  + Compatibility changes
  + Dependency pointers
  + Changing dependencies can cause many errors
    + Changing the implementations of a dependency
    + Changing the dependencies required for an implementation
    + Cyclical?
  + Versioning release chores
  + If action runs again & sees there are changes since the last time there was a merge pull request, versioning, Git tag, & Git release