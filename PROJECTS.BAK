//== ===========================================================================
//                  ***** WORLD OF VIRTUAL DEATH *****
//-----------------------------------------------------------------------------
// THIS PROGRAMME IS RELATED TO A GAME WHICH IS KNWON AS "HANG MAN"...THE USER
// MAY KNOW ABOUT THE GAME WHEN HE GETS THROUHT THE INSTRUCTION GALAXY ONCE.
//-----------------------------------------------------------------------------
//=============================================================================
#include<fstream.h>
#include<conio.h>
#include<ctype.h>
#include<string.h>
#include<dos.h>
#include<process.h>
int time=1,i,l=0,n=0,temp=0;
void stand(int,int,char []); // THE HANG MAN FOR LEVEL 1
void stand1(int,int,char []);// THE HANG MAN FOR LEVEL 2
void title();//     TITLE PAGE
void creater();
void main()
{
clrscr();
char originalword[30],input,wrong[8],infos[500];
int j,u,q,choice,level,p=0,end=0,x=0,o=0,t=0,e=1,playorquit;
creater();
title();
textcolor(10);
{cprintf("                 *****");}
textcolor(1);
{cprintf(" WORLD");}
textcolor(2);
{cprintf(" OF");}
textcolor(3);
{cprintf(" VIRTUAL");}
textcolor(4);
{cprintf(" DEATH");}
textcolor(9);
{cprintf("*****                                ");}
cout<<"\n\n";
textbackground(12);
textcolor(25);
cprintf("\n\nPLEASE ENTER THE OPTION:\n");
textbackground(12);
textcolor(26);
cprintf(" 1-PLAY THE GAME\n");
textbackground(12);
textcolor(14);
cprintf(" 2-INSTRUCTIONS\n");
textbackground(12);
textcolor(23);
cprintf(" 3-EXIT  \n");
textbackground(0);
cout<<"\n";
cin>>choice;
switch(choice)
{
case 1:
{
game:
for(int m=0;;m++)
{
cout<<"CHOOSE YOUR LEVEL TO PLAY:\n1-LEVEL 1\n2-LEVEL 2\n\n";
cin>>level;
if(level>2 || level <1)
{cout<<"PLEASE ENTER THE CORRECT OPTION";
continue;}
else
break;
}
textbackground(12);
clrscr();
cout<<"\n\t\t\tLOADING PLEASE WAIT\n";
textbackground(0);
for(i=0;i<80;i++)
{textcolor(i);
cprintf(".");delay(30);
}
ifstream fin("projlvl1.txt",ios::in);
for(i=0;;i++)
{
textcolor(15);
textbackground(0);
cout<<"\n";
cprintf("ENTER YOUR LUCKY NUMBER(MUST BE RESTRICTED TO 181):");
cout<<"\n\t\t";
cin>>j;
if(j>200 || j<1)
{
if(i<3)
cprintf("UFF!!!!!! I AM MR.RULES ,DONT TRY TO VIOLATE ME ,PLEASE FOLLOW ME");
cout<<"\n";
}
else
break;
if(i==3)
{
cout<<"NOW THATS TOO MUCH.SO I CANT MAKE YOU FURTHER PLAY BECAUSE YOU DOESNT SEEM TO BE INTRESTED IN PLAYING THIS GAME\n-MR.VIRTUAL";
cout<<"\n\t\tBYE BYE!!!!!!!";
delay(15000);
exit(0);
}
}for(i=0;i<j;i++)
{
fin.seekg(p++);
fin>>originalword;
u=strlen(originalword);
if(i>1&& i%2==0)
p=p+u+2;
else
p+=u;
}
clrscr();
u=strlen(originalword);
gotoxy(0,0);
char *userword=new char[u];
////////////////////////////JUST TO MAKE CH1 AS NULL ////////////////////////
for(i=0;i<u;i++)
userword[i]=' ';
////////////////////////////JUST TO MAKE CH1 AS NULL ////////////////////////
while(end==0)
{
if(level==1)
if(time>1)
stand(j,time-1,originalword);//because time has increased already so one step ahead it may proceed if time s given
if(level==2)
if(time>1)
stand1(j,time-1,originalword);
gotoxy(1,1);
textcolor(2);
textcolor(15);
cprintf("\nCONTENT OF YOUR GUESS:\n\b\b\b\b");
for(i=0;i<u;i++)
if(userword[i]==originalword[i])
{cout<<originalword[i]<<" ";}
else
{cout<<"__ ";}
cout<<"\nTHE CHARACTERS WHICH ARE NOT A PART OF YOUR GIVEN WORD:\n";
for(q=0;q<t;q++)
cout<<wrong[q]<<" ";
cout<<"\n";
gotoxy(8,0);
textcolor(15);
cprintf("\n   ENTER THE PRECIOUS CHARACTER:");
gotoxy(27,8); cout<<"É===»";
gotoxy(27,9); cout<<"º   º";
gotoxy(27,10);cout<<"È===¼";
gotoxy(29,9);
cin>>input;
input=toupper(input);
cout<<"\n";
for(i=0;i<u;i++)
if(input==originalword[i]) //BECAUSE t VALUE HAS INCREASED ALREADY
{
userword[i]=originalword[i];
o++;
}
if(o>0)
for(i=100;i<1001;i+=100)
{sound(i);delay(50);}
nosound();
textcolor(6);
textcolor(15);
for(i=0;i<u;i++)
if(userword[i]==originalword[i])
{
cout<<originalword[i]<<" ";
delay(500);
}
else
{cout<<"__ ";delay(500);}
for(i=0;i<u;i++)
if(userword[i]==originalword[i])
x++;
clrscr();
//////////////////////IF o=0 THEN NO WORD IS MATCHING////////////////////////
if(o==0)
{
for(i=1000;i>99;i-=100)
{
sound(i);delay(50);}
nosound();
gotoxy(0,0);
if(level==1)
stand(j,time,originalword);
else
stand1(j,time,originalword);
::time++;
wrong[t++]=input;//FOR THE WRONG WORDS
}
o=0;
for(i=0;i<u;i++)
if(originalword[i]==userword[i])
l++;
if(l==u)
{
end++;
clrscr();
textcolor(10);
textbackground(12);
cprintf(" *****************  CONGRATULATIONS ************************");
cout<<"\n\n";
cprintf("@@@@@@@@@@@@@@@@@  YOU HAVE WON THE GAME  @@@@@@@@@@@@@@@@@@");
cout<<"\n\n";
cprintf("##############  YOU HAVE ESCAPED THE VIRTUAL DEATH  @@@@@@@@@@@@@@");
textbackground(0);
textcolor(154);
gotoxy(56,8);cprintf("É======»");
gotoxy(57,9);cprintf(" *  *");
gotoxy(57,11);cprintf(" È==¼ ");
for(i=9;i<12;i++)
{gotoxy(56,i);cprintf("º");}
for(i=9;i<13;i++)
{gotoxy(63,i);cprintf("º");}
gotoxy(56,12);cprintf("È======¼");
textcolor(158);
for(i=13;i<18;i++)
{gotoxy(60,i);cprintf("º");}
textcolor(155);
/////////////////////////////LEFT HAND///////////////////////////////////////
gotoxy(59,14);cprintf("É");
gotoxy(59,15);cprintf("¼");
gotoxy(57,15);cprintf("==");
gotoxy(56,15);cprintf("È");
gotoxy(56,14);cprintf("º");
/////////////////////////////RIGHT HAND///////////////////////////////////////
gotoxy(61,14);cprintf("»");
gotoxy(61,15);cprintf("È");
gotoxy(62,15);cprintf("==");
gotoxy(64,15);cprintf("¼");
gotoxy(64,14);cprintf("º");
/////////////////////////////LEFT LEG////////////////////////////////////////
textcolor(156);
gotoxy(60,18);cprintf("¼");
gotoxy(59,18);cprintf("É");
gotoxy(59,19);cprintf("¼");
gotoxy(58,19);cprintf("É");
gotoxy(58,20);cprintf("¼");
gotoxy(57,20);cprintf("É");
/////////////////////////////RIGHT LEG///////////////////////////////////////
gotoxy(61,18);cprintf("»");
gotoxy(61,19);cprintf("È");
gotoxy(62,19);cprintf("»");
gotoxy(62,20);cprintf("È");
gotoxy(63,20);cprintf("»");
for(double k=100;k<4000;k+=100)
{sound(k);delay(50);}
nosound();
delay(10000);
exit(0);
}
l=0;
}
fin.close();
delete userword;
break;
}
case 2:
{
clrscr();
cout<<"\t\tWELCOME TO THE INFORMATION GALAXY\n\n";
sound(300);
delay(100);
sound(400);
delay(100);
sound(500);
delay(100);
sound(700);
delay(100);
sound(800);
delay(500);
nosound();
ifstream info("projinfo.txt",ios::in);
while(!info.eof())
{
delay(3000);
info.getline(infos,500);
if(e%2==0)
{
textbackground(135);
textcolor(4); }
else
textbackground(12);
cprintf(infos);
cout<<"\n\n";
textcolor(7);
e++;
}
delay(3000);
for(int l=0;;l++)
{
cout<<"\nARE YOU WILLING TO SAY GOOD BYE TO VIRTUAL DEATH\n1-PLAY\n2-EXIT\n";
cin>>playorquit;
if(playorquit==1)
{
cout<<"NOW LETS GET INTO THE GAME.\n\n";
delay(2000);
goto game;
}
else if(playorquit==2)
goto exitgame;
else
cout<<"\nPLEASE ENTER THE CORRECT OPTION\n-MR.RULES";
}
}
case 3:
exitgame:
textcolor(10);
textbackground(12);
cout<<"\n\n\n\n";
cprintf("          |||||||||||||||||||                 |||||||||||||||||||               ");

cprintf("          ~~~~~~~~~~~~~~~~~~~    THANK YOU    ~~~~~~~~~~~~~~~~~~~               ");
cprintf("          |||||||||||||||||||                 |||||||||||||||||||               ");
sound(500);delay(500);
sound(400);delay(500);
sound(300);delay(500);
sound(400);delay(200);
sound(300);delay(200);
sound(400);delay(200);
sound(500);delay(200);
sound(600);delay(200);
sound(500);delay(200);
sound(400);delay(200);
sound(300);delay(1000);
nosound();
exit(0);
}
getch();
}
/////////////////////////////////////////////////////////////////////////////
//////////////////////////////////DISPLAY CREATER NAME///////////////////////
void creater()
{
textbackground(12);
textcolor(10);
cprintf("A PROJECT CREATED BY");
cout<<"\n\n";
cprintf(" É====»  É====» º    //  É==== É===» º    º                                     ");
cprintf(" º    º  º    º º  //    º     º     º    º                                     ");
cprintf(" º====¼  º    º º//      º     È===» º    º                                     " );
cprintf(" º=»     º====º º\\\\      º====     º º====º                              ");
cprintf("        º È=»   º    º º  \\\\    º         º º    º                               ");
cprintf("       º   È»  º    º º    \\\\  È==== È===¼ º    º                                                                                                                                                                                                     ");
cout<<"\n\n\n";
cout<<"\t\t\t===========================\n";
cout<<"\t\t\t  \\\\        //  º    º\n" ;
cout<<"\t\t\t    \\\\    //    º    º\n" ;
cout<<"\t\t\t      \\\\//      º    º\t\t2015-16\n" ;
cout<<"\t\t\t      //\\\\      º    º\n" ;
cout<<"\t\t\t    //    \\\\    º    º\n" ;
cout<<"\t\t\t  //        \\\\  º    º\n" ;
cout<<"\t\t\t===========================\n\n";
cout<<"KENDRIYA VIDYALAYA GILL NAGAR\n";
delay(4000);
clrscr();
textbackground(0);
}
//===========================================================================
//===========================================================================
//----------------------------TITLE------------------------------------------
//===========================================================================
//===========================================================================
void title()
{
textbackground(0);
for(double k=100;k<4000;k+=100)
{sound(k);delay(50);}
nosound();
for(i=130;i<257;i++)
{
gotoxy(0,i);
textcolor(i);
{
cprintf("|~*~|");
}
}
textcolor(145);
cprintf("|~*~|");
cout<<"\n\n\n\n";
textcolor(10);
{
delay(1000);
cprintf("                 *****");
delay(1000);
}
textcolor(1);
{
cprintf(" WORLD");
delay(1000);
}
textcolor(2);
{
cprintf(" OF");
delay(1000);
}
textcolor(3);
{
cprintf(" VIRTUAL");
delay(1000);
}
textcolor(4);
{
cprintf(" DEATH");
delay(1000);
}
textcolor(9);
{
cprintf("*****                              ");
delay(1000);
}
cout<<"\n\n\n\n";
for(i=130;i<257;i++)
{
gotoxy(0,i);
textcolor(i);
{
cprintf("|~*~|");
}
textcolor(0);
}
textcolor(145);
cprintf("|~*~|");
delay(4000);
textcolor(2);
clrscr();
}
//===========================================================================
//===========================================================================
//--------------------------HANG MAN-----------------------------------------
//===========================================================================
//===========================================================================
void stand(int j,int time,char correctword[])
{
///////////////////////////////LEVEL-1///////////////////////////////////////
switch(time)
{
case 1:
{
/////////////////////////////FIRST FAILURE CASE//////////////////////////////
/////////////////////////////////HANG STAND//////////////////////////////////
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
gotoxy(0,0);
textcolor(15);
break;
}
/////////////////////////////SECOND FAILURE CASE/////////////////////////////
/////////////////////////////////////FACE////////////////////////////////////
case 2:
{
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
textcolor(154);
gotoxy(56,8);cprintf("É======»");
gotoxy(57,9);cprintf(" *  *");
gotoxy(57,11);cprintf(" È==¼ ");
for(i=9;i<12;i++)
{gotoxy(56,i);cprintf("º");}
for(i=9;i<13;i++)
{gotoxy(63,i);cprintf("º");}
gotoxy(56,12);cprintf("È======¼");
gotoxy(0,0);
textcolor(15);
break;
}
/////////////////////////////THIRD FAILURE CASE//////////////////////////////
////////////////////////////////////BODY/////////////////////////////////////
case 3:
{
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
textcolor(154);
gotoxy(56,8);cprintf("É======»");
gotoxy(57,9);cprintf(" *  *");
gotoxy(57,11);cprintf(" È==¼ ");
for(i=9;i<12;i++)
{gotoxy(56,i);cprintf("º");}
for(i=9;i<13;i++)
{gotoxy(63,i);cprintf("º");}
gotoxy(56,12);cprintf("È======¼");
textcolor(158);
for(i=13;i<18;i++)
{gotoxy(60,i);cprintf("º");}
gotoxy(0,0);
textcolor(15);
break;
}
/////////////////////////////FOURTH FAILURE CASE/////////////////////////////
////////////////////////////////LEFT HAND////////////////////////////////////
case 4:
{
gotoxy(1,18);
cout<<"CLUE:\n";
if(j>0 && j<=12)
cout<<"CLUE:\nA WORD RELATED TO PARTS OF COMPUTER\nOR THE BRAND NAME";
if(j>=13 && j<=25)
cout<<"A GENERAL WORD IDES IN CPP TERMINOLOGY";
if(j>=26 && j<=36)
cout<<"ITS A HEADERFILE";
if(j>=37 && j<=44)
cout<<"ITS NOTHING BUT A DATATYPE";
if(j>=45 && j<=57)
cout<<"TERM RELATED TO OOP'S CONCEPTS \n& IMPLEMENTATION OF THOSE CONCEPTS";
if(j>=58 && j<=63)
cout<<"TERM RELATED TO FILE OR MODE OF DECLARATION";
if(j>=64 && j<=76)
cout<<"COMMON KEYWORDS IN C++";
if(j>=77 && j<=90)
cout<<"TERMS RELATED TO BOOLEAN ALGEBRA";
if(j>=91 && j<=106)
cout<<"TERM RELATED TO POINTERS ARRAYS \n& LINKED LIST";
if(j>=107 && j<=121)
cout<<"A TERM RELATED TO SQL QUERY";
if(j>=121 && j<=181)
cout<<"A TERM OR AN ABREVATION RELATED \nTO NETWORKING CONCEPTS";
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
textcolor(154);
gotoxy(56,8);cprintf("É======»");
gotoxy(57,9);cprintf(" *  *");
for(i=9;i<12;i++)
{gotoxy(56,i);cprintf("º");}
for(i=9;i<13;i++)
{gotoxy(63,i);cprintf("º");}
gotoxy(56,12);cprintf("È======¼");
textcolor(158);
for(i=13;i<18;i++)
{
gotoxy(60,i);cprintf("º");}
textcolor(155);
/////////////////////////////LEFT HAND///////////////////////////////////////
gotoxy(59,14);cprintf("É");
gotoxy(59,15);cprintf("¼");
gotoxy(57,15);cprintf("==");
gotoxy(56,15);cprintf("È");
gotoxy(56,14);cprintf("º");
////////////////////////////MOUTH EXPRESSION////////////////////////////////
gotoxy(57,11);cprintf(" ==== ");
gotoxy(0,0);n++;
textcolor(15);
break;
}
/////////////////////////////FIFTH FAILURE CASE//////////////////////////////
/////////////////////////////////RIGHT HAND/////////////////////////////////////
case 5:
{
gotoxy(1,18);
if(j>0 && j<=12)
cout<<"CLUE:\nA WORD RELATED TO PARTS OF COMPUTER\nOR THE BRAND NAME";
if(j>=13 && j<=25)
cout<<"A GENERAL WORD USED IN CPP TERMINOLOGY";
if(j>=26 && j<=36)
cout<<"ITS A HEADERFILE";
if(j>=37 && j<=44)
cout<<"ITS NOTHING BUT A DATATYPE";
if(j>=45 && j<=57)
cout<<"RERM RELATED TO OOP'S CONCEPTS \n& IMPLEMENTATION OF THOSE CONCEPTS";
if(j>=58 && j<=63)
cout<<"TERM RELATED TO FILE OR MODE OF DECLARATION";
if(j>=64 && j<=76)
cout<<"COMMON KEYWORDS IN C++";
if(j>=77 && j<=90)
cout<<"TERMS RELATED TO BOOLEAN ALGEBRA";
if(j>=91 && j<=106)
cout<<"TERM RELATED TO POINTERS ARRAYS \n& LINKED LIST";
if(j>=107 && j<=121)
cout<<"A TERM RELATED TO SQL QUERY";
if(j>=121 && j<=181)
cout<<"A TERM OR AN ABREVATION RELATED \nTO NETWORKING CONCEPTS";
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
textcolor(154);
gotoxy(56,8);cprintf("É======»");
gotoxy(57,9);cprintf(" *  *");
for(i=9;i<12;i++)
{gotoxy(56,i);cprintf("º");}
for(i=9;i<13;i++)
{gotoxy(63,i);cprintf("º");}
gotoxy(56,12);cprintf("È======¼");
textcolor(158);
for(i=13;i<18;i++)
{
gotoxy(60,i);cprintf("º");}
textcolor(155);
/////////////////////////////LEFT HAND///////////////////////////////////////
gotoxy(59,14);cprintf("É");
gotoxy(59,15);cprintf("¼");
gotoxy(57,15);cprintf("==");
gotoxy(56,15);cprintf("È");
gotoxy(56,14);cprintf("º");
/////////////////////////////RIGHT HAND///////////////////////////////////////
gotoxy(61,14);cprintf("»");
gotoxy(61,15);cprintf("È");
gotoxy(62,15);cprintf("==");
gotoxy(64,15);cprintf("¼");
gotoxy(64,14);cprintf("º");
////////////////////////////MOUTH EXPRESSION////////////////////////////////
gotoxy(57,11);cprintf(" ==== ");
gotoxy(0,0);
textcolor(15);
break;
}
/////////////////////////////SIXTH FAILURE CASE///////////////////////////////
////////////////////////////////LEFT LEGS/////////////////////////////////////
case 6:
{
gotoxy(1,18);
if(j>0 && j<=12)
cout<<"CLUE:\nA WORD RELATED TO PARTS OF COMPUTER\nOR THE BRAND NAME";
if(j>=13 && j<=25)
cout<<"A GENERAL WORD USED IN CPP TERMINOLOGY";
if(j>=26 && j<=36)
cout<<"ITS A HEADERFILE";
if(j>=37 && j<=44)
cout<<"ITS NOTHING BUT A DATATYPE";
if(j>=45 && j<=57)
cout<<"TERM RELATED TO OOP'S CONCEPTS \n& IMPLEMENTATION OF THOSE CONCEPTS";
if(j>=58 && j<=63)
cout<<"TERM RELATED TO FILE OR MODE OF DECLARATION";
if(j>=64 && j<=76)
cout<<"COMMON KEYWORDS IN C++";
if(j>=77 && j<=90)
cout<<"TERMS RELATED TO BOOLEAN ALGEBRA";
if(j>=91 && j<=106)
cout<<"TERM RELATED TO POINTERS ARRAYS \n& LINKED LIST";
if(j>=107 && j<=121)
cout<<"A TERM RELATED TO SQL QUERY";
if(j>=121 && j<=181)
cout<<"A TERM OR AN ABREVATION RELATED \nTO NETWORKING CONCEPTS";
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
textcolor(154);
gotoxy(56,8);cprintf("É======»");
gotoxy(57,9);cprintf(" *  *");
for(i=9;i<12;i++)
{gotoxy(56,i);cprintf("º");}
for(i=9;i<13;i++)
{gotoxy(63,i);cprintf("º");}
gotoxy(56,12);cprintf("È======¼");
textcolor(158);
for(i=13;i<18;i++)
{
gotoxy(60,i);cprintf("º");}
textcolor(155);
/////////////////////////////LEFT HAND///////////////////////////////////////
gotoxy(59,14);cprintf("É");
gotoxy(59,15);cprintf("¼");
gotoxy(57,15);cprintf("==");
gotoxy(56,15);cprintf("È");
gotoxy(56,14);cprintf("º");
/////////////////////////////RIGHT HAND///////////////////////////////////////
gotoxy(61,14);cprintf("»");
gotoxy(61,15);cprintf("È");
gotoxy(62,15);cprintf("==");
gotoxy(64,15);cprintf("¼");
gotoxy(64,14);cprintf("º");
////////////////////////////MOUTH EXPRESSION////////////////////////////////
gotoxy(57,11);cprintf(" ==== ");
textcolor(156);
/////////////////////////////LEFT LEG////////////////////////////////////////
gotoxy(60,18);cprintf("¼");
gotoxy(59,18);cprintf("É");
gotoxy(59,19);cprintf("¼");
gotoxy(58,19);cprintf("É");
gotoxy(58,20);cprintf("¼");
gotoxy(57,20);cprintf("É");
gotoxy(0,0);
break;
}
/////////////////////////////SEVENTH FAILURE CASE//////////////////////////////
/////////////////////////////////RIGHT LEG/////////////////////////////////////
case 7:
{
cout<<"THE SIMPLE AND CORRECT WORD WHICH YOU HAVE MISSED IS:\n\n\n";
cout<<"\t\t"<<correctword;
cout<<"\n\n\n   BYEE BYEEE!!!!!!!!!!";
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
textcolor(154);
gotoxy(56,8);cprintf("É======»");
gotoxy(57,9);cprintf(" *  *");
for(i=9;i<12;i++)
{gotoxy(56,i);cprintf("º");}
for(i=9;i<13;i++)
{gotoxy(63,i);cprintf("º");}
gotoxy(56,12);cprintf("È======¼");
textcolor(158);
for(i=13;i<18;i++)
{gotoxy(60,i);cprintf("º");}
textcolor(155);
/////////////////////////////LEFT HAND///////////////////////////////////////
gotoxy(59,14);cprintf("É");
gotoxy(59,15);cprintf("¼");
gotoxy(57,15);cprintf("==");
gotoxy(56,15);cprintf("È");
gotoxy(56,14);cprintf("º");
/////////////////////////////RIGHT HAND///////////////////////////////////////
gotoxy(61,14);cprintf("»");
gotoxy(61,15);cprintf("È");
gotoxy(62,15);cprintf("==");
gotoxy(64,15);cprintf("¼");
gotoxy(64,14);cprintf("º");
/////////////////////////////LEFT LEG////////////////////////////////////////
textcolor(156);
gotoxy(60,18);cprintf("¼");
gotoxy(59,18);cprintf("É");
gotoxy(59,19);cprintf("¼");
gotoxy(58,19);cprintf("É");
gotoxy(58,20);cprintf("¼");
gotoxy(57,20);cprintf("É");
/////////////////////////////RIGHT LEG///////////////////////////////////////
gotoxy(61,18);cprintf("»");
gotoxy(61,19);cprintf("È");
gotoxy(62,19);cprintf("»");
gotoxy(62,20);cprintf("È");
gotoxy(63,20);cprintf("»");
////////////////////////////MOUTH EXPRESSION////////////////////////////////
gotoxy(57,11);
textcolor(156);
cprintf(" É==» ");
for(i=1000;i>99;i-=100)
{sound(i);delay(50);}
sound(200);delay(1000);
nosound();
delay(4000);
exit(0);
}
break;
}
}
/////////////////////////////////////////////////////////////////////////////
///////////////////////////////LEVEL-2///////////////////////////////////////
/////////////////////////////////////////////////////////////////////////////
void stand1(int j,int time,char correctword[])
{
switch(time)
{
case 1:
{
/////////////////////////////FIRST FAILURE CASE//////////////////////////////
/////////////////////////////////HANG STAND//////////////////////////////////
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
gotoxy(0,0);
textcolor(15);
break;
}
/////////////////////////////SECOND FAILURE CASE/////////////////////////////
/////////////////////////////////////FACE////////////////////////////////////
case 2:
{
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
textcolor(154);
gotoxy(56,8);cprintf("É======»");
gotoxy(57,9);cprintf(" *  *");
gotoxy(57,11);cprintf(" È==¼ ");
for(i=9;i<12;i++)
{gotoxy(56,i);cprintf("º");}
for(i=9;i<13;i++)
{gotoxy(63,i);cprintf("º");}
gotoxy(56,12);cprintf("È======¼");
gotoxy(0,0);
textcolor(15);
break;
}
/////////////////////////////THIRD FAILURE CASE//////////////////////////////
////////////////////////////////////BODY/////////////////////////////////////
case 3:
{
gotoxy(1,18);
if(j>0 && j<=12)
cout<<"CLUE:\nA WORD RELATED TO PARTS OF COMPUTER\nOR THE BRAND NAME";
if(j>=13 && j<=25)
cout<<"A GENERAL WORD USED IN CPP TERMINOLOGY";
if(j>=26 && j<=36)
cout<<"ITS A HEADERFILE";
if(j>=37 && j<=44)
cout<<"ITS NOTHING BUT A DATATYPE";
if(j>=45 && j<=57)
cout<<"TERM RELATED TO OOP'S CONCEPTS \n& IMPLEMENTATION OF THOSE CONCEPTS";
if(j>=58 && j<=63)
cout<<"TERM RELATED TO FILE OR MODE OF DECLARATION";
if(j>=64 && j<=76)
cout<<"COMMON KEYWORDS IN C++";
if(j>=77 && j<=90)
cout<<"TERMS RELATED TO BOOLEAN ALGEBRA";
if(j>=91 && j<=106)
cout<<"TERM RELATED TO POINTERS ARRAYS \n& LINKED LIST";
if(j>=107 && j<=121)
cout<<"A TERM RELATED TO SQL QUERY";
if(j>=121 && j<=181)
cout<<"A TERM OR AN ABREVATION RELATED \nTO NETWORKING CONCEPTS";
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
textcolor(154);
gotoxy(56,8);cprintf("É======»");
gotoxy(57,9);cprintf(" *  *");
gotoxy(57,11);cprintf(" È==¼ ");
for(i=9;i<12;i++)
{gotoxy(56,i);cprintf("º");}
for(i=9;i<13;i++)
{gotoxy(63,i);cprintf("º");}
gotoxy(56,12);cprintf("È======¼");
textcolor(158);
for(i=13;i<18;i++)
{gotoxy(60,i);cprintf("º");}
gotoxy(0,0);
textcolor(15);
break;
}
/////////////////////////////FOURTH FAILURE CASE//////////////////////////////
////////////////////////////////////HANDS/////////////////////////////////////
case 4:
{
gotoxy(1,18);
if(j>0 && j<=12)
cout<<"CLUE:\nA WORD RELATED TO PARTS OF COMPUTER\nOR THE BRAND NAME";
if(j>=13 && j<=25)
cout<<"A GENERAL WORD USED IN CPP TERMINOLOGY";
if(j>=26 && j<=36)
cout<<"ITS A HEADERFILE";
if(j>=37 && j<=44)
cout<<"ITS NOTHING BUT A DATATYPE";
if(j>=45 && j<=57)
cout<<"TERM RELATED TO OOP'S CONCEPTS \n& IMPLEMENTATION OF THOSE CONCEPTS";
if(j>=58 && j<=63)
cout<<"TERM RELATED TO FILE OR MODE OF DECLARATION";
if(j>=64 && j<=76)
cout<<"COMMON KEYWORDS IN C++";
if(j>=77 && j<=90)
cout<<"TERMS RELATED TO BOOLEAN ALGEBRA";
if(j>=91 && j<=106)
cout<<"TERM RELATED TO POINTERS ARRAYS \n& LINKED LIST";
if(j>=107 && j<=121)
cout<<"A TERM RELATED TO SQL QUERY";
if(j>=121 && j<=181)
cout<<"A TERM OR AN ABREVATION RELATED \nTO NETWORKING CONCEPTS";
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
textcolor(154);
gotoxy(56,8);cprintf("É======»");
gotoxy(57,9);cprintf(" *  *");
for(i=9;i<12;i++)
{gotoxy(56,i);cprintf("º");}
for(i=9;i<13;i++)
{gotoxy(63,i);cprintf("º");}
gotoxy(56,12);cprintf("È======¼");
textcolor(158);
for(i=13;i<18;i++)
{
gotoxy(60,i);cprintf("º");}
textcolor(155);
/////////////////////////////LEFT HAND///////////////////////////////////////
gotoxy(59,14);cprintf("É");
gotoxy(59,15);cprintf("¼");
gotoxy(57,15);cprintf("==");
gotoxy(56,15);cprintf("È");
gotoxy(56,14);cprintf("º");
/////////////////////////////RIGHT HAND///////////////////////////////////////
gotoxy(61,14);cprintf("»");
gotoxy(61,15);cprintf("È");
gotoxy(62,15);cprintf("==");
gotoxy(64,15);cprintf("¼");
gotoxy(64,14);cprintf("º");
////////////////////////////MOUTH EXPRESSION////////////////////////////////
gotoxy(57,11);cprintf(" ==== ");
gotoxy(0,0);
textcolor(15);
break;
}
/////////////////////////////FIFTH FAILURE CASE//////////////////////////////
////////////////////////////////////LEGS/////////////////////////////////////
case 5:
{
cout<<"THE SIMPLE AND CORRECT WORD WHICH YOU HAVE MISSED IS:\n\n\n";
cout<<"\t\t"<<correctword;
cout<<"\n\n\n   BYEE BYEEE!!!!!!!!!!";
gotoxy(40,5);
textcolor(150);
cprintf("É==================»");
for(i=6;i<25;i++)
{
gotoxy(40,i);cprintf("º");
}
for(i=6;i<8;i++)
{gotoxy(59,i);cprintf("º");}
textcolor(154);
gotoxy(56,8);cprintf("É======»");
gotoxy(57,9);cprintf(" *  *");
for(i=9;i<12;i++)
{gotoxy(56,i);cprintf("º");}
for(i=9;i<13;i++)
{gotoxy(63,i);cprintf("º");}
gotoxy(56,12);cprintf("È======¼");
textcolor(158);
for(i=13;i<18;i++)
{gotoxy(60,i);cprintf("º");}
textcolor(155);
/////////////////////////////LEFT HAND///////////////////////////////////////
gotoxy(59,14);cprintf("É");
gotoxy(59,15);cprintf("¼");
gotoxy(57,15);cprintf("==");
gotoxy(56,15);cprintf("È");
gotoxy(56,14);cprintf("º");
/////////////////////////////RIGHT HAND///////////////////////////////////////
gotoxy(61,14);cprintf("»");
gotoxy(61,15);cprintf("È");
gotoxy(62,15);cprintf("==");
gotoxy(64,15);cprintf("¼");
gotoxy(64,14);cprintf("º");
/////////////////////////////LEFT LEG////////////////////////////////////////
textcolor(156);
gotoxy(60,18);cprintf("¼");
gotoxy(59,18);cprintf("É");
gotoxy(59,19);cprintf("¼");
gotoxy(58,19);cprintf("É");
gotoxy(58,20);cprintf("¼");
gotoxy(57,20);cprintf("É");
/////////////////////////////RIGHT LEG///////////////////////////////////////
gotoxy(61,18);cprintf("»");
gotoxy(61,19);cprintf("È");
gotoxy(62,19);cprintf("»");
gotoxy(62,20);cprintf("È");
gotoxy(63,20);cprintf("»");
////////////////////////////MOUTH EXPRESSION////////////////////////////////
gotoxy(57,11);
textcolor(156);
cprintf(" É==» ");
for(i=1000;i>99;i-=100)
{sound(i);delay(50);}
sound(200);delay(1000);
nosound();
delay(4000);
exit(0);
}
break;
}
}