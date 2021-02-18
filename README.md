### Hello world

- 🔭 I’m currently a senior at Reed College.
  - I'm a TA for fundamental of Computer Science II. 
  - My senior thesis is about optimizing approximation algorithms for the Rural Postman Problem.
- 🌱 I’m job hunting right now. 
  - If your interested, you can contact me at @iwahbe on twitter or on LinkedIn with the same name.



<details><summary>Anything can be complicated. Lets make the simple things simple.</summary>
<p>
  
```rust
fn fizzbuzz(n: usize) {
    let factory = move |div_by: usize, then: Box<dyn Fn(usize)>, otherwise: Box<dyn Fn(usize)>| {
        move |k: usize| {
            if k % div_by == 0 {
                then(k)
            } else {
                otherwise(k)
            }
        }
    };
    macro_rules! box_me {
        ($e: expr) => {
            Box::new($e)
        };
    }
    let print_k = box_me!(|k| println!("{:?}", k));
    let buzz_yes = box_me!(factory(
        5,
        box_me!(|_| println!("fizzbuzz")),
        box_me!(|_| println!("fizz")),
    ));
    let buzz_no = box_me!(factory(5, Box::new(|_| println!("buzz")), print_k));
    let fizz = factory(3, buzz_yes, buzz_no);
    (1..n + 1).for_each(fizz)
}

```

</p>
</details>
