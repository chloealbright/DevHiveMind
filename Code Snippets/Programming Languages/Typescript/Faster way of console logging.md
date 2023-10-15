
console.time('time')
let output = ''

for (let i=0;i<=1000000;i++){
    output+=`${i}\n`
}

console.log(output)
console.timeEnd('time')