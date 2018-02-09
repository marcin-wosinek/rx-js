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

`-` - time; `^` - then; `B` - message; `#` - error

+++

# Promise operators

|        | promise.race() | promise.all() |
|--------|--------|----------|
| `-A`   | | |
| `--B`  | `-A` | `---(ABC)`  |
| `---C` | | |

`-` - time; `A` - message; `()` - synced events 


---

# Observables (RxJs)

+++

# Observables - simple operators

+++

# Observables - higher order operators

+++

# Cold (lazy) observables - unicast

+++

# Hot observables - multicast
