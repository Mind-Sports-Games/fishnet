I. Generate your own key

- [grant your user a role ROLE_SUPER_ADMIN]
- go to [/dev/cli](http://localhost:9663/dev/cli)
- generate the key for your user : `fishnet client create <username>`

II. Use the key

create the file `fishnet.ini` in the root folder of this project

```
[fishnet]
key=<the-one-you-generated>
userbacklog=0
cores=auto
systembacklog=0
```

III. Prepare fishnet

1. SET correct version for rust crate rsffish with key `rsffish` in file `Cargo.toml`
2. run `git submodule update --init --recursive`
3. for analysis (given lila is running on port 9663) :
   - run `cargo run -- --verbose --endpoint=http://localhost:9663/fishnet`
4. for playing vs stockfish bot :
   - start lila-fishnet (on port 9000)
   - run `cargo run -- --verbose --endpoint=http://localhost:9000/fishnet `

In case you need to add extra fairy API config, you can specify the variant.ini file to use by adding : `--variants-ini-file=./variants.ini` to the "cargo run" command
