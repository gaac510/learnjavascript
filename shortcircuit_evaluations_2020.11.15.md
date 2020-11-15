[Shortcircuit Evaluations](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-record-collection/18261)
>... The tracks array is initialized if it does not exist, and then value is pushed into the tracks array. (This step uses shortcircuit evaluation)

```javascript
var collection = {
  2548: {
    albumTitle: 'Slippery When Wet',
    artist: 'Bon Jovi',
    tracks: ['Let It Rock', 'You Give Love a Bad Name']
  },
  2468: {
    albumTitle: '1999',
    artist: 'Prince',
    tracks: ['1999', 'Little Red Corvette']
  },
  1245: {
    artist: 'Robert Palmer',
    tracks: []
  },
  5439: {
    albumTitle: 'ABBA Gold'
  }
};

// Only change code below this line
function updateRecords(object, id, prop, value) {
  if (value === '') delete object[id][prop];
  else if (prop === 'tracks') {
    object[id][prop] = object[id][prop] || []; // this is called shortcircuit evaluation, see below for explanation
    object[id][prop].push(value);
  } else {
    object[id][prop] = value;
  }

  return object;
}
```
`
