# ho-func
Advanced function set

### Array
 - dupIndex  - Find duplicate indexes

```javascript
dupIndex([1, 2, 2, 4, 5, 5, 5, 6, 78, 78, 78, 88, 88, 3, 6, 7], x => x)
```
Output:
```javascript
{
  '2': [ 1, 2 ],
  '5': [ 4, 5, 6 ],
  '6': [ 7, 14 ],
  '78': [ 8, 9, 10 ],
  '88': [ 11, 12 ]
}
```
### Tree
 - totalizer  - Cumulative sum procedure
```javascript
totalizer(({
  tree: [
    {
      a: 1,
      children: [{ score: 20 }, { score: 22 }, { children: [ { score: 10 } ] }]
    }
  ]
}))
```
Output:
```javascript
{ score: 52 }
```
 - list2tree  - Create Tree from list items
```javascript
list2tree({ list: [
  { id: 12, a: 12 },
  { id: 13, a: 22, parent: 12 },
  { id: 14, a: 22, parent: 12 },
  { id: 15, a: 22, parent: 13 }
] })
```
Output:
```javascript
[{
  "id": 12,
  "a": 12,
  "children": [
    {
      "id": 13,
      "a": 22,
      "parent": 12,
      "children": [
        {
          "id": 15,
          "a": 22,
          "parent": 13,
          "children": []
        }
      ]
    },
    {
      "id": 14,
      "a": 22,
      "parent": 12,
      "children": []
    }
  ]
}]
```
 - tree2list  - Create List items from tree
```javascript
tree2list({
  tree: [{
    a: 12,
    children: [{
      b: 23,
      children: [{ c: 23 }]
    }, {
      d: 23
    }]
  }]
})
```
Output:
```javascript
[
  { a: 12, id: '3rH5TqEQbSC0Luw0RAi2oc2MaVLEWgjy' },
  { b: 23, parent: '3rH5TqEQbSC0Luw0RAi2oc2MaVLEWgjy', id: 'gJxvUcoSGhESpbvKAu9xhvYTqVWcL5SH' },
  { c: 23, parent: 'gJxvUcoSGhESpbvKAu9xhvYTqVWcL5SH', id: 'rRCXTckJUXyq8GvcwmB0tKqQrnJeX1Va' },
  { d: 23, parent: '3rH5TqEQbSC0Luw0RAi2oc2MaVLEWgjy', id: 'oe3Qi9yFq6Ts7guxguEtWw73INbGfRFa' }
]
```
 - searchNodes  - search some matched nodes
```javascript
searchNodes({
  tree: [{
    a: 12,
    b: 23,
    children: [
      { a: 12, b: 23, children: [{ a: 12 }] }
    ]
  }],
  filter: x => {
    return x.a === 12
  }
})
```
Output:
```javascript
[
  { a: 12, b: 23, id: 'bO8OfkKGdpkoYIPnX6Z3fMC490musJzM' },
  { a: 12, b: 23, parent: 'bO8OfkKGdpkoYIPnX6Z3fMC490musJzM', id: 'ygkJRyzaRUfdKcMrsMhtrwTVC9VF3H7x' },
  { a: 12, parent: 'ygkJRyzaRUfdKcMrsMhtrwTVC9VF3H7x', id: 'yNJOIvQR6SNKH5Qm8N3MeW9Pb6cPsI7E' }
]
```
 - searchNodeParents  - search some matched nodes parents
```javascript
searchNodeParents({
  tree: [{
    a: 12,
    b: 23,
    children: [
      { a: 12, b: 23, children: [{ a: 12, c: 6 }] }
    ]
  }],
  filter: x => {
    return x.c === 6
  }
})
```
Output:
```javascript
[
  {
    node:
    {
       a: 12,
       c: 6,
       parent: 'LmEkrlmuIPi9thQkH0GoIGRu8S4ramrH',
       id: '5Y9VSlrUDZFQ3JgAbgKuhqGex2fIyyjh'
    },
    parents: [ [Object], [Object] ]
  }
]
```