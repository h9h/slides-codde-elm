---
@title[Learning The Elm Language]

## Was ist Elm
---
## Strangenesses
---
## Functions 1


```elm
-- Named function
isPositive n = n > 0

-- Anonymous function:
\n -> n > 0
```

Elm’s anonymous functions differ from named functions in three ways.

@ul[](false)

- They have no names
- They begin with a "\"
- Their parameters are followed by "->" instead of "="

@ulend

---
## Functions 2

Parameters are separated by space:

```elm
multiply n m = n * m
``` 

All elm functions are curried!

JavaScript functions are "tupled" by default

In JavaScript you **could** write

```JS
  const add = x => y => x + y

  const add2 = add(2)

  add2(4) === add(2)(4) // true
```

---

### No methods, only functions

<table>
  <tr>
    <th width="50%">JavaScript</th>
    <th width="50%">Elm</th>
  </tr>
  <tr>
    <td>"storm".length</td>
    <td>String.length "storm"</td>
  </tr>
  <tr>
    <td>"dredge".toUpperCase()</td>
    <td>String.toUpper "dredge"</td>
  </tr>
  <tr>
    <td>String.fromCharCode(something)</td>
    <td>String.fromChar something</td>
  </tr>
</table>
 

---

### No statements, only expressions

JavaScript:
```JS
const value = a > 0 ? a : -1 * a

if (a > 0) { a } else { -1 * a } // huh?
```

Elm:
```elm
wert = if a > 0 then a else -1 * a
``` 
---

### Operators

@ul[](false)

- Always accept two arguments
- Are functions
- Can be used infix, or prefix as "(op)":
  - 1 + 2 is equivalent to (+) 1 2

@ulend

---

## Collections

List - [1,2,3]

Record - {x = 1, y = "a"}

Tuple - (1,'a')


All are immutable!
---

## Array vs List

<table>
  <tr>
    <th width="50%">JavaScript Array</th>
    <th width="50%">Elm List</th>
  </tr>
  <tr>
    <td>[ 1, 2, 3 ].length</td>
    <td>List.length [ 1, 2, 3 ]</td>
  </tr>
  <tr>
    <td>[ "one fish", "two fish" ][0]</td>
    <td>List.head [ "one fish", "two fish" ]</td>
  </tr>
  <tr>
    <td>[ "one fish", "two fish" ][1]</td>
    <td>No arbitrary position-based element access</td>
  </tr>
  <tr>
    <td>[ 1, 2 ].concat([ 3, 4 ])</td>
    <td> [ 1, 2 ] ++ [ 3, 4 ]</td>
  </tr>
  <tr>
    <td>[ 1, 2 ].push(3)</td>
    <td> Cannot be modified; use e.g. append instead</td>
  </tr>
  <tr>
    <td>[ 1, "Paper", 3 ]</td>
    <td>All elements in a list must have a consistent type</td>
  </tr>
</table>

---

## Objects vs Records

<table>
  <tr>
    <th width="50%">JavaScript Object</th>
    <th width="50%">Elm Record</th>
  </tr>
  <tr>
    <td>{ name: "Li", cats: 2 }</td>
    <td>{ name = "Li", cats = 2 }</td>
  </tr>
  <tr>
    <td>({ name: "Li", cats: 2 }).cats</td>
    <td>{ name = "Li", cats = 2 }.cats <em>or</em> .cats { name: "Li", cats: 2 } </td>
  </tr>
  <tr>
    <td>({ name: "Li", cats: 2 })["cats"]</td>
    <td>No access by name</td>
  </tr>
  <tr>
    <td>({ name: "Li", cats: 2 }).cats = 3</td>
    <td>Cannot be modified. (New cat? New record!)</td>
  </tr>
  <tr>
    <td>{ NAME: "Li", CATS: 2 }</td>
    <td>Field names can’t start with uppercase letters</td>
  </tr>
  <tr>
    <td>Object.keys({ name: "Li", cats: 5 })</td>
    <td>No listing of field names is available on demand</td>
  </tr>
</table>
---

## Elm Collection Properties

<table>
  <tr>
    <th width="33%">List</th>
    <th width="33%">Record</th>
    <th width="33%">Tuple</th>
  </tr>
  <tr>
    <td>Variable Length</td>
    <td>Fixed Length</td>
    <td>Fixed Length</td>
  </tr>
  <tr>
    <td>Can Iterate Over</td>
    <td>Cannot Iterate Over</td>
    <td>Cannot Iterate Over</td>
  </tr>
  <tr>
    <td>No Names</td>
    <td>Named Fields</td>
    <td>No Names</td>
  </tr>
  <tr>
    <td>Single Type</td>
    <td>Any Types</td>
    <td>Any Types, max. 3-Tupel</td>
  </tr>
  <tr>
    <td>Immutable</td>
    <td>Immutable</td>
    <td>Immutable</td>
  </tr>
</table

---

## Elm Architecture

@img[](assets/img/elm-architecture.png)

---
