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
| `-A` <br /> `--B` <br /> `---C` | `-A` | `---(ABC)`  |

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

`-` time; `e` event; `()` synced events; `|` complete

+++

# Observables - simple operators

+++

# Observables - higher order operators

+++

# Cold (lazy) observables - unicast

+++

# Hot observables - multicast
