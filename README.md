# cg
computer graphics
#include<stdio.h>
#include<math.h>
#include<GL/glut.h>
#define ESC 27;
void display3();
float ro=0;
GLfloat a=0,b=0,c=0,d=0,xc=35,e=0;
void myinit()
{
glClearColor(0.0,0.749,1.00,1.0);
glMatrixMode(GL_PROJECTION);
gluOrtho2D(0.0,300.0,0.0,300.0);
}

void circle_draw(GLint xc,GLint yc,GLint r)
{
float i,angle=0;
glBegin(GL_POLYGON);
for(i=0;i<360;i+=10)
{
angle=3.142/180*i;
glVertex2f(xc+cos(angle)*r,yc+sin(angle)*r);
}
glEnd();
}

void key(unsigned char key,int x,int y)
{
	switch(key)
	{
		case 32:if(a!=280){
						if(ro<40)ro+=0.25;	
							 a++;
							 glutPostRedisplay();
					}
		

			else{ ro=0;
				e++;
				display3();
			}
		if(a==e){
			a=0;
			e=0;
			}
                              
			break;
			
   		case 27:exit(0);
	}
}

void display()
{
GLint xc=35,yc=250,r=15,d=5;
glClear(GL_COLOR_BUFFER_BIT);

glColor3f(1.0,1.0,0);
glPointSize(1.0);
circle_draw(xc+a,yc,r);
//rays
glColor3f(0,0,0);
glBegin(GL_LINES);
glVertex2i(15+a,245);
glVertex2i(0+a,240);
glVertex2i(20+a,235);
glVertex2i(5+a,200);
glVertex2i(30+a,230);
glVertex2i(25+a,200);
glVertex2i(40+a,230);
glVertex2i(43+a,200);
glVertex2i(49+a,235);
glVertex2i(65+a,200);
glVertex2i(55+a,245);
glVertex2i(80+a,230);
glEnd();


glColor3f(0.0,0.0,0.0);
glRasterPos2i(90,270);
glutBitmapString(GLUT_BITMAP_TIMES_ROMAN_24,"Press and hold SPACE BAR ");
if(a!=0)
{
glColor3f(0.0,0.0,0.0);
glRasterPos2i(10,280);
glutBitmapString(GLUT_BITMAP_TIMES_ROMAN_24,"DAY VISION ");
}

//road
glColor3f(0.0,0.0,0.0);
glBegin(GL_POLYGON);
glVertex2i(0,15);
glVertex2i(300,15);
glVertex2i(300,0);
glVertex2i(0,0);
glEnd();
glColor3f(1,1,1);
glBegin(GL_LINES);
glVertex2i(20,7);
glVertex2i(60,7);
glVertex2i(80,7);
glVertex2i(120,7);
glVertex2i(140,7);
glVertex2i(180,7);
glVertex2i(200,7);
glVertex2i(240,7);
glVertex2i(260,7);
glVertex2i(300,7);
glEnd();
//land
glColor3f(0.627,0.322,0.176);
glBegin(GL_POLYGON);
glVertex2i(0,15);
glColor3f(0.727,0.322,0.176);
glVertex2i(0,90);
glColor3f(0.920,0.322,0.176);
glVertex2i(250,90);
glColor3f(0.837,0.322,0.176);
glVertex2i(250,15);
glEnd();
//channel
glColor3f(0.098,0.098,0.439);
glBegin(GL_POLYGON);
glVertex2i(157,90);
glVertex2i(155,92);
glVertex2i(200,92);
glVertex2i(200,90);
glEnd();
//power station
glColor3f(1.0,0.894,0.769);
glBegin(GL_POLYGON);
glVertex2i(195,90);
glVertex2i(195,160);
glVertex2i(300,160);
glVertex2i(300,90);
glEnd();
glColor3f(1.0,0.0,0.0);
glRasterPos2i(220,150);
glutBitmapString(GLUT_BITMAP_HELVETICA_12,"POWER STATION");

//home 1
glColor3f(0.957,0.643,0.376);
glBegin(GL_POLYGON);
glVertex2i(250,15);
glVertex2i(250,150);
glVertex2i(300,150);
glVertex2i(300,15);
glEnd();
glColor3f(0.871,0.722,0.529);
glBegin(GL_POLYGON);
glVertex2i(250,150);
glVertex2i(255,155);
glVertex2i(300,155);
glVertex2i(300,150);
glEnd();
glColor3f(0.502,0.00,0.0);
glBegin(GL_POLYGON);
glVertex2i(290,15);
glVertex2i(290,35);
glVertex2i(280,35);
glVertex2i(280,15);
glEnd();

glColor3f(0.690,0.769,0.871);
glBegin(GL_POLYGON);
glVertex2i(295,45);
glVertex2i(295,55);
glVertex2i(285,55);
glVertex2i(285,45);
glEnd();

glColor3f(0.690,0.769,0.871);
glBegin(GL_POLYGON);
glVertex2i(270,65);
glVertex2i(270,75);
glVertex2i(260,75);
glVertex2i(260,65);
glEnd();

glColor3f(0.690,0.769,0.871);
glBegin(GL_POLYGON);
glVertex2i(295,85);
glVertex2i(295,95);
glVertex2i(285,95);
glVertex2i(285,85);
glEnd();

glColor3f(0.690,0.769,0.871);
glBegin(GL_POLYGON);
glVertex2i(295,120);
glVertex2i(295,135);
glVertex2i(260,135);
glVertex2i(260,120);
glEnd();

glColor3f(0.957,0.643,0.376);
glBegin(GL_LINES);
glVertex2i(285,120);
glVertex2i(285,135);
glEnd();

glColor3f(0.957,0.643,0.376);
glBegin(GL_LINES);
glVertex2i(270,120);
glVertex2i(270,135);
glEnd();

//home 2
glColor3f(0.576,0.439,0.859);
glBegin(GL_POLYGON);
glVertex2i(240,15);
glVertex2i(240,75);
glVertex2i(180,75);
glVertex2i(180,15);
glEnd();
glColor3f(0.6,0.5,0.6);
glBegin(GL_POLYGON);
glVertex2i(180,75);
glVertex2i(185,80);
glVertex2i(242,80);
glVertex2i(240,75);
glEnd();
glColor3f(0.416,0.353,0.804);
glBegin(GL_POLYGON);
glVertex2i(240,15);
glVertex2i(242,15);
glVertex2i(242,80);
glVertex2i(240,75);
glEnd();

glColor3f(0.502,0.502,0.0);
glBegin(GL_POLYGON);
glVertex2i(240,75);
glVertex2i(240,100);
glVertex2i(220,110);
glVertex2i(200,100);
glVertex2i(200,75);
glEnd();

glColor3f(0.282,0.239,0.545);
glBegin(GL_POLYGON);
glVertex2i(190,15);
glVertex2i(190,35);
glVertex2i(205,35);
glVertex2i(205,15);
glEnd();

glColor3f(0.690,0.769,0.871);
glBegin(GL_POLYGON);
glVertex2i(215,50);
glVertex2i(225,50);
glVertex2i(225,40);
glVertex2i(215,40);
glEnd();

glColor3f(0.690,0.769,0.871);
glBegin(GL_POLYGON);
glVertex2i(230,95);
glVertex2i(225,95);
glVertex2i(225,90);
glVertex2i(230,90);
glEnd();

glColor3f(0.373,0.620,0.627);
glBegin(GL_POLYGON);
glVertex2i(210,75);
glVertex2i(210,85);
glVertex2i(220,85);
glVertex2i(220,75);
glEnd();

glColor3f(0.0,0.2,0.7);
glBegin(GL_LINES);
glVertex2i(220,110);
glVertex2i(195,98);
glEnd();

glColor3f(0.0,0.2,0.7);
glBegin(GL_LINES);
glVertex2i(220,110);
glVertex2i(245,98);
glEnd();


glColor3f(0.184,0.310,0.30);
glBegin(GL_POLYGON);
glVertex2i(0,90);
glVertex2i(20,100);
glVertex2i(140,100);
glVertex2i(160,90);
glEnd();

//pannel 1 
glColor3f(0.184,0.30,0.30);
glBegin(GL_POLYGON);
glVertex2i(40,100);
glVertex2i(40,130);
glVertex2i(43,132);
glVertex2i(43,100);
glEnd();

glColor3f(0.00,0.0,0.123);
glBegin(GL_POLYGON);
glVertex2i(20,110+ro);
glVertex2i(17,113+ro);
glVertex2i(60,158-ro);
glVertex2i(63,154-ro);  	 
glEnd();

	
//pannel 2
glColor3f(0.184,0.30,0.30);
glBegin(GL_POLYGON);
glVertex2i(80,100);
glVertex2i(80,130);
glVertex2i(83,132);
glVertex2i(83,100);
glEnd();

glColor3f(0.00,0.0,0.123);
glBegin(GL_POLYGON);
glVertex2i(60,110+ro);
glVertex2i(57,113+ro);
glVertex2i(100,158-ro);
glVertex2i(103,154-ro);
glEnd();
//pannel 3
glColor3f(0.184,0.30,0.30);
glBegin(GL_POLYGON);
glVertex2i(120,100);
glVertex2i(120,130);
glVertex2i(123,132);
glVertex2i(123,100);
glEnd();

glColor3f(0.00,0.0,0.123);
glBegin(GL_POLYGON);
glVertex2i(100,110+ro);
glVertex2i(97,113+ro);
glVertex2i(140,158-ro);
glVertex2i(143,154-ro);
glEnd();

//street light 1
glColor3f(0.0,0.0,0.0);
glBegin(GL_POLYGON);
glVertex2i(10,15);
glVertex2i(10,60);
glVertex2i(12,60);
glVertex2i(12,15);
glEnd();

glColor3f(0.878, 1.000, 1.000);
glBegin(GL_POLYGON);
glVertex2i(10,60);
glVertex2i(7,67);
glVertex2i(15,67);
glVertex2i(12,60);
glEnd();

//street light 2
glColor3f(0.0,0.0,0.0);
glBegin(GL_POLYGON);
glVertex2i(50,15);
glVertex2i(50,60);
glVertex2i(52,60);
glVertex2i(52,15);
glEnd();
glColor3f(0.878, 1.000, 1.000);
glBegin(GL_POLYGON);
glVertex2i(50,60);
glVertex2i(47,67);
glVertex2i(55,67);
glVertex2i(52,60);
glEnd();

//street light 3
glColor3f(0.0,0.0,0.0);
glBegin(GL_POLYGON);
glVertex2i(90,15);
glVertex2i(90,60);
glVertex2i(92,60);
glVertex2i(92,15);
glEnd();
glColor3f(0.878, 1.000, 1.000);
glBegin(GL_POLYGON);
glVertex2i(90,60);
glVertex2i(87,67);
glVertex2i(95,67);
glVertex2i(92,60);
glEnd();

//street light 4
glColor3f(0.0,0.0,0.0);
glBegin(GL_POLYGON);
glVertex2i(130,15);
glVertex2i(130,60);
glVertex2i(132,60);
glVertex2i(132,15);
glEnd();
glColor3f(0.878, 1.000, 1.000);
glBegin(GL_POLYGON);
glVertex2i(130,60);
glVertex2i(127,67);
glVertex2i(135,67);
glVertex2i(132,60);
glEnd();

//street light 5
glColor3f(0.0,0.0,0.0);
glBegin(GL_POLYGON);
glVertex2i(170,15);
glVertex2i(170,60);
glVertex2i(172,60);
glVertex2i(172,15);
glEnd();
glColor3f(0.878, 1.000, 1.000);
glBegin(GL_POLYGON);
glVertex2i(170,60);
glVertex2i(167,67);
glVertex2i(175,67);
glVertex2i(172,60);
glEnd();

bus();

glutSwapBuffers();

glFlush();
}

void bus()
{
//bus
glColor3f(0.5,0.0,0.0);
glBegin(GL_POLYGON);
glVertex2i(30+a,15);
glVertex2i(75+a,15);
glVertex2i(75+a,45);
glVertex2i(30+a,45);
glEnd();

glColor3f(1.0,1.0,1.0);
glBegin(GL_POLYGON);
glVertex2i(68+a,35);
glVertex2i(74+a,35);
glVertex2i(74+a,43);
glVertex2i(68+a,43);
glEnd();

GLint xc=40,yc=15,r=5,f=25;
glColor3f(0.5,0.5,0.5);
glDrawBuffer(GL_BACK);
glPointSize(1.0);
circle_draw(xc+a,yc,r);

glColor3f(0.5,0.5,0.5);
glDrawBuffer(GL_BACK);
glPointSize(1.0);
circle_draw(xc+a+f,yc,r);

glFlush();
}

void display3()
{

GLint xc=25,yc=250,r=15;

display();
//night vision
glColor3f(0,0,1);
glBegin(GL_POLYGON);
glVertex2i(0,300);
glVertex2i(0,90);
glVertex2i(20,100);
glVertex2i(140,100);
glVertex2i(160,90);
glVertex2i(195,90);
glVertex2i(195,160);
glVertex2i(340,160);
glVertex2i(340,300);
glEnd();
//channel
glColor3f(0,0,0);
glBegin(GL_POLYGON);
glVertex2i(157,90);
glVertex2i(155,92);
glVertex2i(195,92);
glVertex2i(195,90);
glEnd(); 
//windows of home 1
glColor3f(1.0,1.0,0);
glBegin(GL_POLYGON);
glVertex2i(295,45);
glVertex2i(295,55);
glVertex2i(285,55);
glVertex2i(285,45);
glEnd();

glColor3f(1.0,1.0,0);
glBegin(GL_POLYGON);
glVertex2i(270,65);
glVertex2i(270,75);
glVertex2i(260,75);
glVertex2i(260,65);
glEnd();

glColor3f(1.0,1.0,0);
glBegin(GL_POLYGON);
glVertex2i(295,85);
glVertex2i(295,95);
glVertex2i(285,95);
glVertex2i(285,85);
glEnd();

glColor3f(1.0,1.0,0);
glBegin(GL_POLYGON);
glVertex2i(295,120);
glVertex2i(295,135);
glVertex2i(260,135);
glVertex2i(260,120);
glEnd();

glColor3f(0.957,0.643,0.376);
glBegin(GL_LINES);
glVertex2i(285,120);
glVertex2i(285,135);
glEnd();

glColor3f(0.957,0.643,0.376);
glBegin(GL_LINES);
glVertex2i(270,120);
glVertex2i(270,135);
glEnd();

//windows for home 2
glColor3f(1,1,0);
glBegin(GL_POLYGON);
glVertex2i(215,50);
glVertex2i(225,50);
glVertex2i(225,40);
glVertex2i(215,40);
glEnd();

glColor3f(1,1,0);
glBegin(GL_POLYGON);
glVertex2i(230,95);
glVertex2i(225,95);
glVertex2i(225,90);
glVertex2i(230,90);
glEnd();

//pannel 1 
glColor3f(0.184,0.30,0.30);
glBegin(GL_POLYGON);
glVertex2i(40,100);
glVertex2i(40,130);
glVertex2i(43,132);
glVertex2i(43,100);
glEnd();

glColor3f(0.00,0.0,0.123);
glBegin(GL_POLYGON);
glVertex2i(20,110);
glVertex2i(17,113);
glVertex2i(60,158);
glVertex2i(63,154);
glEnd();
//pannel 2
glColor3f(0.184,0.30,0.30);
glBegin(GL_POLYGON);
glVertex2i(80,100);
glVertex2i(80,130);
glVertex2i(83,132);
glVertex2i(83,100);
glEnd();

glColor3f(0.00,0.0,0.123);
glBegin(GL_POLYGON);
glVertex2i(60,110);
glVertex2i(57,113);
glVertex2i(100,158);
glVertex2i(103,154);
glEnd();
//pannel 3
glColor3f(0.184,0.30,0.30);
glBegin(GL_POLYGON);
glVertex2i(120,100);
glVertex2i(120,130);
glVertex2i(123,132);
glVertex2i(123,100);
glEnd();

glColor3f(0.00,0.0,0.123);
glBegin(GL_POLYGON);
glVertex2i(100,110);
glVertex2i(97,113);
glVertex2i(140,158);
glVertex2i(143,154);
glEnd();
//moon
glColor3f(1,1,1);
glDrawBuffer(GL_BACK);
glPointSize(1.0);
circle_draw(xc+e,yc,r);

//street light 1
glColor3f(1,1,0);
glBegin(GL_POLYGON);
glVertex2i(7,67);
glVertex2i(15,67);
glColor3f(1,1,1);
glVertex2i(2,40);
glVertex2i(20,40);
glColor3f(0.9,0.9,0);
glVertex2i(15,67);
glEnd();

//street light 2
glColor3f(1,1,0);
glBegin(GL_POLYGON);
glVertex2i(47,67);
glVertex2i(55,67);
glColor3f(1,1,1);
glVertex2i(42,40);
glVertex2i(60,40);
glColor3f(1,1,0);
glVertex2i(55,67);
glEnd();

//street light 3
glColor3f(1,1,0);
glBegin(GL_POLYGON);
glVertex2i(87,67);
glVertex2i(95,67);
glColor3f(1,1,1);
glVertex2i(100,40);
glVertex2i(82,40);
glColor3f(1,1,0);
glVertex2i(95,67);
glEnd();

//street light 4
glColor3f(1,1,0);;
glBegin(GL_POLYGON);
glVertex2i(127,67);
glVertex2i(135,67);
glColor3f(1,1,1);
glVertex2i(140,40);
glVertex2i(122,40);
glColor3f(1,1,0);
glVertex2i(135,67);
glEnd();

//street light 5
glColor3f(1,1,0);
glBegin(GL_POLYGON);
glVertex2i(167,67);
glVertex2i(175,67);
glColor3f(1,1,1);
glVertex2i(180,40);
glVertex2i(162,40);
glColor3f(1,1,0);
glVertex2i(175,67);
glEnd();

glColor3f(0.0,0.0,0.0);
glRasterPos2i(120,280);
glutBitmapString(GLUT_BITMAP_TIMES_ROMAN_24,"Press and hold SPACE BAR");

if(a!=0)
{
glColor3f(0.0,0.0,0.0);
glRasterPos2i(10,280);
glutBitmapString(GLUT_BITMAP_TIMES_ROMAN_24,"NIGHT VISION \n\n\n\n\n The generated solar energy can be seen in the form of light i.e in homes and street lights");
}
bus();
glFlush();
}


void main(int argc,char **argv)
{
glutInit(&argc,argv);
glutInitDisplayMode(GLUT_SINGLE|GLUT_SINGLE);
glutInitWindowSize(1000,700);
glutInitWindowPosition(150,50);
glutCreateWindow("solar energy");
glutDisplayFunc(display);
glutKeyboardFunc(key);
glutSwapBuffers();
myinit();
glutMainLoop();
}
