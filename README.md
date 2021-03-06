![image](box-img-sm.png)

# Bento 🍱

A Truffle box that explores the various ways in which you can extend Truffle's functionality through exec scripts, plugins, etc.

> Warning - Copious emojis have been used in the preparation of this box 

## Executable Scripts 🍣

Simple example...

```
> truffle develop
truffle(develop)> exec scripts/example.js
```

Interacting with an existing chain...

```
> truffle develop
truffle(develop)> exec scripts/bento.js
```

## Truffle Plugin 🍤

Single command...

```
> cd plugin
> npm link
> cd ..
> npm link /path/to/project/plugin
> truffle run boooom
```

> Note that `npm link`-ing is useful while developing the plugin as any changes are immediately reflected

Command with parameters...

```
> truffle run boooom liftoff
> truffle run boooom landing
> truffle run boooom landing https://moon.io
```

A more complete example of a plugin is available [here](https://github.com/kevinbluer/truffle-plugin-caramel).

## Truffle Box 🥒

To package a repository you'll need the following...

- [truffle-box.json](truffle-box.json)
- [box-img-lg.png](box-img-lg.png)
- [box-img-sm.png](box-img-sm.png)

As you may have spotted, this is repository is actually already a box meaning you could install it via the following:

```
> truffle unbox kevinbluer/bento
```

Boxes can be include plugins pre-installed. For example, this [plugin](https://github.com/kevinbluer/truffle-plugin-caramel) is added as a dependency, meaning you can use it immediately (although you'll need to add your [Pinata](https://pinata.cloud/) details first).

```
> truffle run caramel list
```

## Alternatives Approaches 🦞

Another example of an means of extending Truffle's functionality is the [OpenZeppelin Upgrades](https://docs.openzeppelin.com/upgrades-plugins/1.x/) plugin. This is different to the Truffle Plugins system mention above in that's more of a framework and pattern for both deploying and managing upgradable contracts.

Try it yourself...

```
> truffle develop
truffle(develop)> compile --all
truffle(develop)> migrate --to 3
truffle(develop)> i = await BentoBase.deployed()
truffle(develop)> i.getValue() 
truffle(develop)> i.setValue(888) // 🚫
truffle(develop)> migrate --f 4
truffle(develop)> i = await BentoUpgrade.deployed()
truffle(develop)> i.setValue(888)
```

## Other

- `npx` is your friend :)