<script>
    import P5 from 'p5-svelte';
  
    const sketch = (p5) => {
      let img;
      let bgImg; 
      let gridSize = 30;
      let grids = [];
  
      p5.preload = () => {
        img = p5.loadImage('./src/lib/images/assets/sorrento_col.jpg');
        bgImg = p5.loadImage('./src/lib/images/assets/sorrento.jpg'); 
      };
  
      p5.setup = () => {
        p5.createCanvas(800, 200);
        p5.background(bgImg);

  
        let numberX = p5.round(p5.windowWidth / gridSize);
        let numberY = p5.round(p5.windowHeight / gridSize);
        let gridSizeX = p5.windowWidth / numberX;
        let gridSizeY = p5.windowHeight / numberY;
  
        for (let i = 0; i < numberX; i++) {
          for (let j = 0; j < numberY; j++) {
            let index = j * numberX + i;
            let xPos = i * gridSizeX;
            let yPos = j * gridSizeY;
            grids[index] = new Grid(xPos, yPos, gridSizeX, gridSizeY);
          }
        }
      };
  
      p5.draw = () => {
        let numberX = p5.round(p5.windowWidth / gridSize);
        let numberY = p5.round(p5.windowHeight / gridSize);
        let gridSizeX = p5.windowWidth / numberX;
        let gridSizeY = p5.windowHeight / numberY;
        let indexX = p5.floor(p5.mouseX / gridSizeX);
        let indexY = p5.floor(p5.mouseY / gridSizeY);
        let index = indexY * numberX + indexX;
  
        if (!grids[index].revealed) {
          grids[index].reveal();
        }
  
        for (let grid of grids) {
          grid.display();
        }
      };
  
      class Grid {
        constructor(x, y, w, h) {
          this.x = x;
          this.y = y;
          this.w = w;
          this.h = h;
          this.revealed = false;
        }
  
        display() {
          if (this.revealed) {
            p5.image(img, this.x, this.y, this.w, this.h, this.x, this.y, this.w, this.h);
          }
        }
  
        reveal() {
          this.revealed = true;
        }
      };
    };
  </script>
  
  <P5 {sketch} />