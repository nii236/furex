# furex
A simple flexbox-layout library for ebiten

## Usage

```go
import "github.com/yotahamada/furex"

func (g *Game) initUI() {
	// root flex container
	g.rootFlex := furex.NewFlex(0, 0, screenWidth, screenHeight)
	g.rootFlex.Direction = furex.Column
	g.rootFlex.Justify = furex.JustifySpaceBetween

	// flex item: box0
	b0 := furex.NewBox(100, 100, color.RGBA{0xff, 0, 0, 0xff})
	g.rootFlex.AddChild(b0)

	// flex item: box1
	b1 := furex.NewBox(100, 100, color.RGBA{0, 0xff, 0, 0xff})
  g.rootFlex.AddChild(b1)
}

func (g *Game) Update() {
  // Update the flex layout and it's children
  g.rootFlex.Update()
}

func (g *Game) Draw(screen *ebiten.Image) {
  // Draws children in the containers
	g.rootFlex.Draw(screen)
}
```