# chess
# Project Title and purpose

 We will work as a team to figure out a way for making each of the pieces move and behave individually.  Trying to recreate the original chess and how its played.  With the sprites for the pieces, we will use a sprite creator online and import the picture.  The hardest part for us will be to create the check method. This method will have to check every other opponents piece to see if it is in check. Overall, the system will be a program for two players to play chess against each other.


### Difficulties or opportunities you encountered along the way.

The toughest part was...

getting the pieces to move on the board.

### Most interesting piece of your code and explanation for what it does.

I would say that this is the most interesting thing of my code because it allows the pieces to be taken and it also makes it so the pieces can move.

void mousePressed() {
  for (int i = 0; i < 8; i ++) {
    for (int j = 0; j < 8; j ++) {
      if (mouseX>i*BLOCKX&&mouseX<i*BLOCKX+BLOCKX&&mouseY>j*BLOCKY&&mouseY<j*BLOCKY+BLOCKY) { //what square was clicked
        if(clicked){
          for(int w=0; w<possibleX.size(); w++){
            if(i==possibleX.get(w)&& j==possibleY.get(w)){ //blue spot
              bucky.get(clickedPos).setX(i);
              bucky.get(clickedPos).setY(j);
              for(int m=0; m<bucky.size(); m++){
                 if(bucky.get(m).getX()==i && bucky.get(m).getY()==j && (whiteTurn&&!bucky.get(m).getwhite() || !whiteTurn && bucky.get(m).getwhite()))  {   // another piece there and not own color
                   bucky.remove(m);
                 }
              }
              whiteTurn= !(whiteTurn);
              updatemegaCrap();
              clicked=false;
              draw();
            }
          }
        }
        
        
        
        
        for (int k=0; k<bucky.size(); k++) {
          if (bucky.get(k).getwhite()==whiteTurn&&bucky.get(k).getX()==i&&bucky.get(k).getY()==j)
          {
            clickedx=i;
            clickedy=j;
            clicked=true;
            clickedPos=k;
            possibleX = new ArrayList<Integer>();
            possibleY = new ArrayList<Integer>();
            bucky.get(k).moves();
          }
        }
        
        
        
      }
    }
  }
}




This is the code that moves down the tree as decisions are made.  It gets each value from both left and right and also casts the value to a String.  If the progressions arrives at the leaf nodes, those values are printed.
## Built With

* [Processing](https://processing.org/) - The IDE used

## Authors

* **Billie Thompson** 


## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
