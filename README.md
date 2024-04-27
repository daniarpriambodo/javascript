# javascript
const express = require('express')
const app = express()
const port = 3000

app.get('/nama', (req,res) => {
    res.send('Nama  : Daniar Priambodo')
})

app.post('/login',(req,res) => {
    console.log({requestFromOutside : req.body})
    res.send('Login Berhasil')
})

app.listen(port, () => {
    console.log("Example app listening on port "+port)
})
