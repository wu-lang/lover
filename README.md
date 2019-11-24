<img align="right" width="30%" height="30%" src="https://i.ibb.co/3hnWTkt/love-wu.png" alt="wu_dragon">

# Love
A simple wrapper for the Love2D game engine, for game development with Wu.

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


### License

[MIT License](https://github.com/nilq/love/blob/master/LICENSE)
