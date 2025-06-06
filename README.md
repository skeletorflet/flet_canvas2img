# flet_canvas2img
Flet_canvas2img allows you to save a Flet Canvas as an Image
## Installation
```
pip install git+https://github.com/Benitmulindwa/flet_canvas2img.git
```
## Example
```python
import math
import flet as ft
import flet.canvas as cv
from flet_canvas2img import canvas2img


def main(page: ft.Page):
    stroke_paint = ft.Paint(stroke_width=2, style=ft.PaintingStyle.STROKE)
    fill_paint = ft.Paint(style=ft.PaintingStyle.FILL)
    cp = cv.Canvas(
        [
            cv.Circle(100, 100, 50, stroke_paint),
            cv.Circle(80, 90, 10, stroke_paint),
            cv.Circle(84, 87, 5, fill_paint),
            cv.Circle(120, 90, 10, stroke_paint),
            cv.Circle(124, 87, 5, fill_paint),
            cv.Arc(70, 95, 60, 40, 0, math.pi, paint=stroke_paint),
        ],
        width=float("inf"),
        expand=True,
    )

    page.add(cp)

    # Save the whole canvas as an image
    canvas2img(cp.shapes)

ft.app(main)

```
## Params
`canvas2img()` gets the following parameters:

- `shapes:` List of shapes from a Flet canvas.
- `width:` Width of the output image(int).
- `height:` Height of the output image(int).
- `background_color:` Background color of the image.
- `can_save:` If True it will save the image else the output image will not be saved, by default it's `True`.
- `save_path:` Path to save the generated image, by default it is `output.png`
