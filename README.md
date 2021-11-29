# rstoml

<a href="https://www.npmjs.com/package/rstoml"><img src="https://img.shields.io/npm/v/rstoml.svg"></img></a>
<a href="https://github.com/rainy-me/rstoml/actions/workflows/lint.yaml"><img src="https://github.com/rainy-me/rstoml/workflows/Lint/badge.svg"></img></a>
<a href="https://github.com/rainy-me/rstoml/actions/workflows/CI.yaml"><img src="https://github.com/rainy-me/rstoml/workflows/CI/badge.svg"></img></a>


[`toml-rs`](https://github.com/alexcrichton/toml-rs) re-exported via [`napi-rs`](https://github.com/napi-rs/napi-rs)


## Install

- `pnpm add rstoml`
- `yarn add rstoml`
- `npm add rstoml`

## Usage

API interface is slightly different from the original `rstoml` lib and more close to js conventions.


```ts
import toml from "rstoml"

toml.parse("foo = 'bar'")
// -> { foo: 'bar' }

toml.parse(`
ip = '127.0.0.1'

[keys]
github = 'xxxxxxxxxxxxxxxxx'
travis = 'yyyyyyyyyyyyyyyyy'
`)
// -> {
//      ip: '127.0.0.1',
//      keys: {
//        github: 'xxxxxxxxxxxxxxxxx',
//        travis: 'yyyyyyyyyyyyyyyyy',
//      }
//    }

toml.parseBuffer(Buffer.from("foo = 'bar'", "utf-8"))
// -> { foo: 'bar' }

toml.stringify({ foo: 'a\nb\nc' })
// -> `foo = "a\nb\nc"`

toml.stringify({ foo: 'a\nb\nc' }, { pretty: true })
// -> foo = '''
//    a
//    b
//    c'''
```

## Benchmark

Not available now. As all I want for now is a stable toml lib.

## why

I can't found a maintained node toml library.