#include <iostream>
#include <fstream>
#include <cstring>
using namespace std;


void fancyqueen(){
  //ofstream fout("fancyqueen.txt");
    int q[8], c = 0, count = 0;
    q[0] = 0;
    int i, j, k, l;
    typedef string box[5][7];
    box bb, wb, bq, wq, *board[8][8]; //box is same as char

  while ( true ) // nc c != -1
  {
        c++;
  if ( c == 8 ){
  count++;
    cout << "Solution: " << count << endl;

  //fill in bb = black box and wb = whitebox
  for ( i = 0; i < 5; i++ )
    for ( j = 0; j < 7; j++){
      wb[i][j] = " "; //white board
      bb[i][j] = "\u2593"; //balck board
      //wq[i][j] = " "; //white queens
      //bq[i][j] = '='; //black queens
  }
   static box wq = { {"\u2593","\u2593","\u2593","\u2593","\u2593","\u2593","\u2593"},
                     {"\u2593"," ","\u2593"," ","\u2593"," ","\u2593"},
                     {"\u2593"," ","\u2593"," ","\u2593"," ","\u2593"},
                     {"\u2593"," "," "," "," "," ","\u2593"},
                     {"\u2593","\u2593","\u2593","\u2593","\u2593","\u2593","\u2593"} };

   static box bq = { {" "," "," "," "," "," "," "},
                     {" ","\u2593"," ","\u2593"," ","\u2593"," "},
                     {" ","\u2593"," ","\u2593"," ","\u2593"," "},
                     {" ","\u2593","\u2593","\u2593","\u2593","\u2593"," "},
                     {" "," "," "," "," "," "," "} };

  //fill board with pointers to bb and wb in alternate positions
  for ( i = 0; i < 8; i++ )
    for ( j = 0; j < 8; j++ )
      if ( (i + j) % 2 == 0) //if i + j = even, then print wb
        board[i][j] = &wb; //address of wb
      else 
        board[i][j] = &bb; //address of bb

   for( i=0; i<8; i++ )
      if( (i+q[i]) % 2 == 0 )
         board[q[i]][i] = &bq;
      else
         board[q[i]][i] = &wq;

  //print the board via the pointers in array board
  //first print upper border
  cout << "   ";
  for ( i = 0; i < 29; i++ )
    cout << "_ ";
    cout << endl;

  //now print the board
  for ( i = 0; i < 8; i++ ) //for each board row
    for ( k = 0; k < 5; k++){ //for each box row
      cout << "   " << '|'; //print left border
      for ( j = 0; j < 8; j++ ) //for each board column
        for ( l = 0; l < 7; l++) //for each box column
          cout << (*board[i][j])[k][l];
        cout << '|' << endl; //at the end of line print bar and then newline
      }

  //before exiting print lower border
  cout << "   ";
  for ( i = 0; i < 29; i++ )
    cout << "- ";
    cout << endl;
}

  q[c] = -1;

  while (1) // nr
    {
      q[c]++;

      if (q[c] == 8) 
      {
           c--;
          if ( c == -1 ) return;
            continue;
       }

       bool checked = true;

      for (int i = 0; i < c; i++) {
          if (q[i] == q[c] || c - i == abs(q[c] - q[i])) {
               checked = false;
               break;
              //goto nr;  // break for, and continue inner while
          } 
       }

       if ( checked ) break;
       else           continue;

      // break inner while    //goto nc;
    }       
  }
  //fout.close();
  return;
}

int main(){
  fancyqueen();
}
