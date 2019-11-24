<img align="right" width="30%" height="30%" src="https://i.ibb.co/3hnWTkt/love-wu.png" alt="wu_dragon">

# Lover
A wrapper for the Love2D game engine, for game development with Wu. Function names have been changed from CamelCase to snake_case to be consistent with Wu code-style.

## Example

```fsharp
import love

Player: struct {
  x: float
  y: float
  speed: float
}

implement Player {
  update: fun(dt: float) {
    if love keyboard is_down("left") {
      self x -= self speed * dt
    }
    if love keyboard is_down("right") {
      self x += self speed * dt
    }
  }
}

player := new Player {
  x: 100
  y: 100
}

love update = fun(dt: float) {
  player update(dt)
}

love draw = fun {
  love graphics set_color(255, 100, 255)
  love graphics rectangle("fill", player x, player y, 20, 20)
}
```


### License

[MIT License](https://github.com/nilq/love/blob/master/LICENSE)
