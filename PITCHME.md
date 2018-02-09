# Promises 

vs

# observables

+++

# modeling delay 

vs 

# modeling time

---

# Promise

```
try {
  let value = doStuff();

  /* .. use the value .. */
} catch (e) {
  /* .. clean up .. */
}
```

```
let promise = doStuff();

promise.then((value) => {
  /* .. use the value .. */
}).catch((e) => {
  /* .. clean up .. */
}
```

+++

# Promise over time

|        | `--^`  | `-----^` |
|--------|--------|----------|
| `---B` | `---B` | `-----B` |
| `---#` | `---#` | `-----#` |

`-` time  `^` then  `B` message `#` error

+++

# Promise operators

|        | promise.race() | promise.all() |
|--------|--------|----------|
| `-A` <br /> `--B` <br /> `---C` | <br />  `-A` | <br />  `---(ABC)`  |

`-` time 

`A` message 

`()` synced events 

---

# Observables (RxJs)

```
rx.Observable.of(1, 2, 3);
// (1,2,3)|

rx.Observable.interval(1000);
// 0---1---2---3---4--

rx.Observable.fromEvent(element, 'click');
// ---e--e-------e----
```

`-` time

`e` event

`()` synced events

`|` complete


+++

# Observables - transformation operators

```
source = ..
// 0-1-2-3-4|

source.map(x => x * 2)
// 0-2-4-6-8|

source.bufferTime(1000);
// ----0-1-2-3-4|

source.scan((x, y) => x + y);
// 0-1-3-6-10|
```

+++

# Observables - filter operators

```
source = ..
// 0-1-2-3-4|

source.filter(x => x > 2)
// ------3-4|

source.take(3);
// 0-1-2|

```

+++

# Observables - repeat & retry

```
source1 = ..
// 0--1--2--3--4|

source2.repeat(2)
// 0--1--2--3--40--1--2--3--4|

source2 = ..
// 0---1---2---3#

source2.retry(2)
// 0---1---2---30---1---2---3#
```

+++

# Observables - combination operators

```
source1 = ..
// 0--1--2--3--4|
source2 = ..
// 0---1---2---3|

source1.merge(source2)
//(00)11-2-23--(34)|

source1.concat(source2)
// 0--1--2--3--40---1---2---3|
```

---

# Cold (lazy) observables - unicast

+++

# Hot observables - multicast
