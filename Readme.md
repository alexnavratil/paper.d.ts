# How to use this paper.js typings definition file
First put it into your project directory, where your typescript compiler can find this definition file.

Now you can use it for example within an Angular 2 Component:

```
/**
 * Created by alexnavratil on 06.08.16.
 */
import { Component, AfterViewInit } from "@angular/core";

@Component({
    selector: 'my-canvas',
    template: '<canvas id="myCanvas" resize></canvas>',
})

export class MyCanvasComponent implements AfterViewInit{

    ngAfterViewInit() {
        let canvas = <HTMLCanvasElement>(document.getElementById("myCanvas"));
        paper.setup(canvas);
        var path = new paper.Path();
        path.strokeColor = 'black';
        var start = new paper.Point(100, 100);
        path.moveTo(start);
        path.lineTo(start.add(new paper.Point(200, -50)));
        paper.view.draw();
    }
}
```

NOTE: Don't forget to also include the script tag which imports the paper.js file (or the minified version)
