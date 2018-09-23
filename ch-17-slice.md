## Срез
*Срезом* является ссылка на последовательность однотипных данных.
```rust
fn max(arr: &[u16]) -> u16 {
    if arr.len() == 0 {
        return 0;
    }
    let mut max = arr[0];
    for i in 1..arr.len() {
        if arr[i] > max {
            max = arr[i];
        }
    }
    max
}

fn main() {
    let array = [283, 107, 152, 116, 195, 208, 173, 310];
    println!("{}", max(&array));
    println!("{}", max(&[]));

    let range = 2..5;
    let slice_ref = &array[range];
    println!("{}", max(slice_ref));
}

```
[Rust Playground](https://play.rust-lang.org/?gist=2c912f899677329e096852a8a9d4a7c3&version=stable&mode=debug&edition=2015)

*Ссылка на срез* &[T] содержит 1) ссылку на начало данных и 2) количество этих данных.

Обратите внимание, что в Rust нельзя использовать значение, размер которого неизвестен в момент компиляции. Поэтому можно использовать ссылочные данные, а не сами данные. Это очень важно понять.

Переменные данного типа (срез) могут изменяться (`mut`).

### Домашнее задание
Напишите программу, в которой переменная типа срез будет изменяться.