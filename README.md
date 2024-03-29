# :rotating_light: No longer under active development :rotating_light:
> This project is no longer under active development, however, it should continue to work indefinitely, unless NodeJS changes something dramatically.

---

# JSONifyArgs!

JSONifyArgs quite literally does what it says on the tin: it takes the command line arguments of a NodeJS script, and pops them into a handy-dandy JSON object!

# Args

What does JSONifyArgs count as an argument? Any string in an array you pass in, so long as it begins with `--` (it no longer uses `process.argv` by default). JSONifyArgs doesn't support shorthand (e.g., `-h` instead of `--help`, but if it gets enough interest, I may add it. 😉). You can always add support for it yourself if you like, by forking JSONifyArgs on GitHub!

Also, boolean arguments can be set by `--boolean=true`, but by their very existence they are set to true, so you would get the same result by typing `--boolean`.

# Examples?

Sure!
```
// ------------
// | index.js |
// ------------
const jsonifyArgs = require('jsonifyArgs') // Require JSONifyArgs

let args = jsonifyArgs(process.argv) // Get the arguments from process.argv

let wordOne = args.wordOne || 'HELLO'
let wordTwo = args.wordTwo || 'WORLD'
let rickRoll = args.surprise

console.log(`${wordOne} ${wordTwo}!`)
if(rickRoll) console.log('Never gonna give you up, never gonna let you down...')

```
`node index` would output
```
HELLO WORLD!
```
`node index --wordOne=Rick --wordTwo=Astley --surprise` would output
```
Rick Astley!
Never gonna give you up, never gonna let you down...
```
