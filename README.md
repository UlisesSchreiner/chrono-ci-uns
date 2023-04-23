# Cronometro
[![Build Status](https://app.travis-ci.com/UlisesSchreiner/chrono-ci-uns.svg?branch=master)](https://app.travis-ci.com/UlisesSchreiner/chrono-ci-uns)
[![Coverage Status](https://coveralls.io/repos/github/UlisesSchreiner/chrono-ci-uns/badge.svg?branch=master)](https://coveralls.io/github/UlisesSchreiner/chrono-ci-uns?branch=master)

Un cronometro que cuenta y descuenta

## Instalación

```
npm install proyecto-2c-crono
```

## Uso

### Contador
```
const modulo = require('proyecto-2c-crono');

const cont = new modulo.Contador(2);

var d = cont.start().subscribe(
    data =>  {
        console.log(data);
        if (data === 'FINISH') {
            d.unsubscribe();
        }
    }
);
//Espera estos resultados
00:00:00
00:00:01
FINISH

```

### Descontador
```
const modulo = require('proyecto-2c-crono');

const cont = new modulo.Descontador(4);

var d = cont.start().subscribe(
    data =>  {
        console.log(data);
        if (data === 'FINISH') {
            d.unsubscribe();
        }
    }
);//Espera estos resultados
00:00:04
00:00:03
00:00:02
00:00:01
FINISH
```