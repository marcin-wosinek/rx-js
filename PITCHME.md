# Promises 

vs

# observables

---

# modeling delay 

vs 

# modeling time

+++

# Promise

---

# Promise over time

|        | `--^`  | `-----^` |
|--------|--------|----------|
| `---B` | `---B` | `-----B` |
| `---#` | `---#` | `-----#` |

---

# Promise operators

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

# Observables (RxJs)

---

# Observables - simple operators

---

# Observables - higher order operators

+++

# Cold (lazy) observables - unicast

---

# Hot observables - multicast
