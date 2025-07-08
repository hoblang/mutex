# mutex - simple testing library for hoblang

`mutex` library provides thread-safe mutex wrappers for values

## Usage

```hob
import mutex;

var v = mutex.new.<i32>(1);
defer v.free();

final gotValue: i32 = v.get().unwrap(); # should be 1
v.set(2).unwrap();

final valueRef: *i32 = v.lock().unwrap();
# value ref usage is safe here
v.unlock().unwrap();

# valueRef here unsafe
```

