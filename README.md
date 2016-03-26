//Midterm-Takehome
//By John Duran

String title = "Tail of the Sea";

float boatX, boatY;
float nemoX, nemoY;
float calvinX, calvinY;
int nemoscore, calvinscore, boatscore;
float horizon;


void setup() {
  size (800, 640); // size of screen
  ellipseMode (CENTER);
  horizon = height/2;
 // nemospeed = 1;
  boatX = horizon;
  boatY = 150;
  calvinX = 600;
  calvinY = 585;
  nemoX = width/2;
  nemoY = height/2;
  nemoscore = 0;
  calvinscore = 0;
  

}

void draw() {
  scene();
  nemo();
  calvin();
  boat();
 // action();
  messages();
  
}


void scene() {
  background (50, 200, 255);
  fill ( 100, 200, 150);
  noStroke();
  //rectMode ( CORNERS );
  rect (0, 200, width, height);
}

   // fish
void nemo() {
  fill ( 0 );
  stroke ( 255 );
  ellipse ( nemoX + 40, nemoY - 18, 15, 15);
  
  noStroke();
  fill ( 255, 204, 204 );
  ellipse ( nemoX, nemoY, 120, 50 );

  //dorsal fin
  fill ( 255, 204, 204 );
  triangle ( nemoX - 100, nemoY - 20, nemoX - 100, nemoY + 20, nemoX, nemoY );

  // tail
  fill ( 255, 204, 204 );
  triangle ( nemoX  - 30, nemoY, nemoX + 30, nemoY, nemoX, nemoY - 50);

  // mouth
  stroke ( 255, 0, 0 );
  strokeWeight ( 4 );
  line ( nemoX + 20, nemoY  + 10, nemoX + 50, nemoY + 10 );
}

// boat
 void boat() {
  fill (255, 0, 0 ); 
  rect ( boatX, boatY, 100, 50 );
  triangle ( boatX - 55, boatY, boatX, boatY + 50, boatX, boatY ); 
  rect( boatX + 30, boatY - 30, 40, 30 );
  fill( 0 );
  text( "Chicken of the Sea", boatX - 15, boatY + 20 );
  text( boatscore, boatX + 45, boatY - 15 );
}

// calvin
void calvin() {
  noStroke();
  fill ( 255, 255, 0 );
  ellipse ( calvinX, calvinY, 80, 40 );
  fill ( 0, 255, 255 );
  rect ( calvinX - 70, calvinY - 5, 30, 10 );
  rect ( calvinX + 40, calvinY - 5, 30, 10 );
  fill ( 255, 0, 255 );
  rect ( calvinX - 30, calvinY + 15, 10, 10 );
  rect ( calvinX - 30, calvinY - 25, 10, 10 );
  rect ( calvinX + 20, calvinY - 25, 10, 10 );
  rect ( calvinX + 20, calvinY + 15, 10, 10 );
}

//void action() {
  //if nemoX < 
  

void messages(){ //Text function 
  fill(0);
  textSize(20);
  text(title, width/2.5,20);
  textSize(12);
  text("Catch fish by clicking on boat or crawler.", width/4,40);
  text("(Or use keys: 'b' for boat, 'c' for crawler, r to reset, q to quit.)",width/4,60 );
  fill(0);
  textSize(12);
 // text(author,width/40,height/1.01);
  fill (0);
  text ( "Calvin", calvinX - 25, calvinY );
  text ( "Nemo", nemoX - 20, nemoY );
  //text(" Your score is:"+boatscore,10,10 );
  text ( "BOAT:", width / 1.3, 20 );
  text ( "TUNA:", width / 1.3, 35 );
  text ( "CRAB:", width / 1.3, 50 );
  text ( nemoscore, nemoX - 10, nemoY + 15 );
  text ( calvinscore, calvinX - 10, calvinY + 15 );
}
