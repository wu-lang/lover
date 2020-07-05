<div align="center">
    <a href="https://github.com/wu-lang/wu" target="_blank">
        <img src="https://i.ibb.co/3hnWTkt/love-wu.png" alt="Wu Dragon Heart" width="140" height="140"></img>
    </a>
</div>

<h1 align="center">Lover</h1>
<h3 align="center">A strongly typed Wu wrapper for the Love2D game engine.</h3>

Building your games in Wu and with Lover will massively reduce runtime errors and make for better scalability. Lover provides a wide-scale Wu framework for game development through the latest version of Love2D. Let's go.

## Wu?

Wu is a gradually typed, Rust-inspired programming language that compiles to Lua. The language is designed with scalability and ease-of-use in mind, originally striving to be a solid alternative to Lua and MoonScript - but with **types** and more *rusty*.

## Example

```fsharp
import lover

Player: struct {
  x: float
  y: float
  speed: float
}

implement Player {
  update: fun(self, dt: float) {
    if lover keyboard isDown("left") {
      self x -= self speed * dt
    }
    if lover keyboard isDown("right") {
      self x += self speed * dt
    }
  }
}

player := new Player {
  x: 100
  y: 100
  speed: 100
}

update: fun(dt: float) {
  player update(dt)
}

draw: fun {
  lover graphics push()
  lover graphics scale(3, 3)

  lover graphics setColor(1, 0, 1)
  lover graphics rectangle("fill", player x, player y, 20, 20)
  lover graphics print("Love2D but with Wu", 10, 10)

  lover graphics pop()
}

lover setUpdate(update)
lover setDraw(draw)
```

### Roadmap

The current wrapper will provide you with the basic tools to make a fully functioning desktop game. The rest of the engine are being plugged in as we speak. ;)

- [ ] `love.audio`
- [ ] `love.data`
- [ ] `love.event`
- [ ] `love.filesystem`
- [ ] `love.font`
- [x] `love.graphics`
- [ ] `love.image`
- [ ] `love.joystick`
- [ ] `love.keyboard`
- [ ] `love.math`
- [ ] `love.mouse`
- [x] `love.physics`
- [ ] `love.sound`
- [ ] `love.system`
- [ ] `love.thread`
- [ ] `love.timer`
- [ ] `love.touch`
- [ ] `love.video`
- [ ] `love.window`

### License

[MIT License](https://github.com/nilq/love/blob/master/LICENSE)
