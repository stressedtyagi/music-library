/***************************************************************************
**                                                                        **
**                                                                        **
**		         $ PROJECT BY Divyanshu Tyagi $                           **
**                                                                        **
**                                                                        **
**                                                                        **
***************************************************************************/
//HEADER FILES//
#include <graphics.h>
#include <fstream.h>
#include <process.h>
#include <stdlib.h>
#include <string.h>
#include <ctype.h>
#include <conio.h>
#include <stdio.h>
#include <math.h>
#include <dos.h>
#include <dir.h>

//GLOBAL VARIABLES//
int crac = 0, sign = 0, crs = 0;
char admin_pass[20];

//CLASSES//
class managemu
{
public:
	char name[10];
	char account[20];
} mulist[500];

class manage
{
public:
	char name[20];
	char pass[20];
} list[10];

class music
{
public:
	char script[500];
} music;

class account
{
public:
	char name[20];
	char pass[20];
} account;

//FUNCTIONS//
void welcome();
void admin();
void about();

//HOME FUNCTIONS//
/**/ /*************************************************************/ /**/
/**/ void home();													 /**/
/**/ void home_arc();												 /**/
/**/ void home_bubble();											 /**/
/**/ void home_box();												 /**/
/**/ void home_column();											 /**/
/**/ void home_text();												 /**/
/**/ void home_opt();												 /**/
/**/ /*************************************************************/ /**/
																	 //END HOME FUNCTIONS//

//ACCOUNTS AND LIBRARY//
/**/ /*************************************************************/ /**/
/**/ void account_sign_up();										 /**/
/**/ void account_sign_in();										 /**/
/**/ void account_sign_inout();										 /**/
/**/ void account_edit();											 /**/
/**/ void account_del();											 /**/
/**/ void account_pch();											 /**/
/**/ void reset_data();
void uninstall();													 /**/
/**/ void sign_in_msg();											 /**/
/**/ void library();												 /**/
/**/ void library_add_new();										 /**/
/**/ void library_disco();											 /**/
/**/ void library_sound_play(char);									 /**/
/**/ void library_save();											 /**/
/**/ void library_delete();											 /**/
/**/ void library_play();											 /**/
/**/ /*************************************************************/ /**/
//END ACCOUNTS AND LIBRARY//

//FUNCTIONS END//

void main()
{

	//CHANGE DIRECTORY//
	mkdir("\\music");
	chdir("\\music");

	ifstream fin, fincr;
	ofstream fout;

	//GRAPHIC INITIALISATION//

	int gd = DETECT, gm, x, y;
	initgraph(&gd, &gm, "C:\\TURBOC3\\BGI"); //Initializing Graphics Mode

	cleardevice();

	welcome();

	fin.open("admin.dat", ios::in | ios::binary);
	if (!fin)
	{
		fin.close();
		admin();
	}
	else
	{
		fin.read((char *)&admin_pass, sizeof(admin_pass));
		if (!strcmp(admin_pass, ""))
		{
			fin.close();
			admin();
		}
		else
			fin.close();
	}

	fin.open("manage.lis", ios::in | ios::binary);
	if (!fin)
	{
		fin.close();
		fout.open("manage.lis", ios::out | ios::binary);
		fout.write((char *)&list, sizeof(list));
		fout.close();
	}
	else
		fin.close();

	fin.open("managemu.lis", ios::in | ios::binary);
	if (!fin)
	{
		fin.close();
		fout.open("managemu.lis", ios::out | ios::binary);
		fout.write((char *)&mulist, sizeof(mulist));
		fout.close();
	}
	else
		fin.close();

	fin.open("tac.data", ios::in | ios::binary);
	if (!fincr)
	{
		fin.close();
		fout.open("tac.data", ios::out | ios::binary);
		crac = 0;
		fout.write((char *)&crac, sizeof(crac));
		fout.close();
	}
	else
		fin.close();

	fincr.open("tmu.dat", ios::in | ios::binary);
	if (!fincr)
	{
		fincr.close();
		ofstream foutcr("tmu.dat", ios::out | ios::binary);
		crs = 0;
		foutcr.write((char *)&crs, sizeof(crs));
		foutcr.close();
	}
	else
		fincr.close();

	home();
}

void welcome()
{
	setbkcolor(12);
	setcolor(12);

	//HEADER//
	for (int i = 5; i <= 600; i += 130)
	{

		circle(7 + i, 20, 25);
		setfillstyle(5, YELLOW);
		floodfill(7 + i, 20, 12);

		circle(30 + i, 75, 28);
		setfillstyle(1, CYAN);
		floodfill(30 + i, 75, 12);

		circle(70 + i, 15, 35);
		setfillstyle(1, LIGHTGREEN);
		floodfill(70 + i, 15, 12);

		circle(90 + i, 75, 25);
		setfillstyle(5, LIGHTCYAN);
		floodfill(90 + i, 75, 12);
	}

	//FOOTER//
	for (i = 5; i <= 600; i += 130)
	{
		int j = 385;

		circle(7 + i, 20 + j, 25);
		setfillstyle(5, YELLOW);
		floodfill(7 + i, 20 + j, 12);

		circle(30 + i, 75 + j, 28);
		setfillstyle(1, CYAN);
		floodfill(30 + i, 75 + j, 12);

		circle(70 + i, 15 + j, 35);
		setfillstyle(1, LIGHTGREEN);
		floodfill(70 + i, 15 + j, 12);

		circle(90 + i, 75 + j, 25);
		setfillstyle(5, LIGHTCYAN);
		floodfill(90 + i, 75 + j, 12);
	}

	//WELCOME TEXT//
	settextstyle(6, 0, 25);
	int j = 130;
	for (i = 70; i < 85; i++, j++)
	{
		if (i < 77)
			setcolor(BLUE);
		else
			setcolor(LIGHTCYAN);

		outtextxy(i, j, "WELCOME");
		delay(100);
	}
	getch();
}

void admin()
{
	cleardevice();
	setbkcolor(YELLOW);

	setcolor(LIGHTRED);
	circle(320, 0, 350);
	setfillstyle(1, LIGHTRED);
	floodfill(320, 0, LIGHTRED);

	//TITLE//
	setcolor(WHITE);
	settextstyle(0, 0, 4);

	outtextxy(45, 5, "   SET ADMIN PASS");

	setcolor(CYAN);
	settextstyle(0, 0, 2);
	outtextxy(225, 82, "Pass:");

	gotoxy(45, 6);

	ifstream fincr, fin;
	ofstream foutcr, fout;

	foutcr.open("admin.dat", ios::out | ios::binary);
	foutcr.close();
	gets(admin_pass);

	if (strlen(admin_pass) < 5 || strlen(admin_pass) < 5 || strlen(admin_pass) > 20 || strlen(admin_pass) > 20)
	{
		cleardevice();
		setbkcolor(YELLOW);
		setcolor(LIGHTRED);
		rectangle(0, 190, 640, 290);
		setfillstyle(1, LIGHTRED);
		floodfill(0 + 50, 190 + 5, LIGHTRED);

		setcolor(YELLOW);
		settextstyle(0, 0, 3);
		outtextxy(0, 235, "PASS MUST HAVE 5-20 CHARS");
		delay(1000);
		admin();
	}

	fout.open("admin.dat", ios::out | ios::binary);
	fout.write((char *)&admin_pass, sizeof(admin_pass));
	fout.close();
	cleardevice();
	setbkcolor(YELLOW);
	setcolor(LIGHTRED);
	rectangle(0, 190, 640, 290);
	setfillstyle(1, LIGHTRED);
	floodfill(0 + 50, 190 + 5, LIGHTRED);

	setcolor(YELLOW);
	settextstyle(0, 0, 3);
	outtextxy(0, 235, " SETTING UP ADMIN ACCOUNT");
	delay(1000);
}

void about()
{
	char opt;
	cleardevice();
	setbkcolor(WHITE);

	setcolor(LIGHTRED);
	circle(320, 0, 350);
	setfillstyle(1, LIGHTRED);
	floodfill(320, 0, LIGHTRED);

	//TITLE//
	setcolor(WHITE);
	settextstyle(0, 0, 4);
	outtextxy(40, 5, "THE MUSIC LIBRARY");
	outtextxy(170, 40, " PROJECT");

	setcolor(CYAN);
	settextstyle(0, 0, 3);

	outtextxy(85, 112, " BY Divyanshu Tyagi ");
	setcolor(WHITE);
	settextstyle(0, 0, 1);
	outtextxy(120, 150, "Visit - https://www.linkedin.com/in/divyanshutyagi/");
	setcolor(CYAN);
	rectangle(0, 450, 640, 480);
	setfillstyle(1, CYAN);
	floodfill(0 + 50, 450 + 5, CYAN);

	setcolor(WHITE);
	settextstyle(0,0,2);
	outtextxy(0, 455, "[H]OME                            E[X]IT");

	opt = getche();
	tolower(opt);
	switch (opt)
	{

	case 'h':
		home();
		break;
	case 'x':
		exit(0);
		break;
	default:
		about();
		break;
	}
}

void home()
{
	cleardevice();
	home_arc();
	home_text();
	home_text();
	home_opt();
}

void home_arc()
{
	setbkcolor(LIGHTRED);
	//MENU ARC//
	cleardevice();
	setcolor(CYAN);
	circle(35, 240, 200);
	setfillstyle(1, YELLOW);
	floodfill(35, 240, CYAN);

	home_box();
	home_bubble();
	home_box();	   //BOX CORRECTION//
	home_column(); //COLUMN CORRECTION//
				   //END MENU ARC//
}

void home_bubble()
{
	int i, j, k = 0;
	for (i = 0; i <= 6 * 75; i += 75)
	{
		for (j = 0; j <= 1200; j += 150)
		{

			setcolor(YELLOW);
			circle(-450 + j + k, 25 + i, 25);
			setfillstyle(4, YELLOW);
			floodfill(-450 + j + k, 25 + i, YELLOW);
		}
		k += 75;
	}
}

void home_box()
{

	for (int i = 0, j = 0; i < 5; i++, j++)
	{
		if (i < 4)
		{
			setcolor(CYAN);
			rectangle(410 + i, 120 + j, 590 + i, 320 + j);
			setfillstyle(1, YELLOW);
			floodfill(410 + 50 + i, 120 + 5 + j, CYAN);
		}
		else
		{
			setcolor(12);
			rectangle(410 + i, 120 + j, 590 + i, 320 + j);
			setfillstyle(1, YELLOW);
			floodfill(410 + 50 + i, 120 + 5 + j, LIGHTRED);
		}
	}
	home_column();
}

void home_column()
{
	if (sign == 0)
	{
		setcolor(CYAN);
		//NAME//
		rectangle(425, 175, 585, 195);
		setfillstyle(1, WHITE);
		floodfill(425 + 50, 175 + 5, CYAN);
		//PASSWORD//
		rectangle(425, 220, 585, 240);
		setfillstyle(1, WHITE);
		floodfill(425 + 50, 220 + 5, CYAN);
		//SIGN UP//
		rectangle(452, 270, 560, 295);
		setfillstyle(1, CYAN);
		floodfill(452 + 50, 270 + 5, CYAN);
	}
	else
	{
		//SIGN UP//
		setcolor(CYAN);
		rectangle(452, 270, 560, 295);
		setfillstyle(1, CYAN);
		floodfill(452 + 50, 270 + 5, CYAN);
	}

	//EXIT CIRCLE//
	circle(630, 400, 40);
	setfillstyle(1, CYAN);
	floodfill(630, 400, CYAN);
}

void home_text()
{
	//TITLE//
	setcolor(CYAN);
	settextstyle(0, 0, 4);
	outtextxy(45, 5, "THE MUSIC LIBRARY");

	//MENU TEXT//
	setcolor(CYAN);
	settextstyle(5, 0, 3);
	outtextxy(5, 120, "[1] Library");
	outtextxy(5, 180, "[2] About Us");
	outtextxy(5, 240, "[3] Edit Account");
	//END MENU TEXT//

	if (sign == 0)
	{
		//SIGN IN COLUMN//
		setcolor(LIGHTRED);
		settextstyle(10, 0, 1);
		outtextxy(445, 120, "SIGN [I]N");
		setcolor(CYAN);
		settextstyle(6, 0, 1);
		outtextxy(428, 170, "NAME:");
		outtextxy(428, 215, "PASS:");
		setcolor(WHITE);
		settextstyle(1, 0, 1);
		outtextxy(457, 270, "SIGN [U]P");
		//END SIGN IN COLUMN//
	}
	else
	{
		setcolor(CYAN);
		settextstyle(0, 0, 2);
		outtextxy(445, 130, "WELCOME");
		setcolor(LIGHTRED);
		settextstyle(0, 0, 2);
		outtextxy(425, 150, account.name);
		setcolor(WHITE);
		settextstyle(1, 0, 1);
		outtextxy(457, 270, "SIGN [O]UT");
	}

	//EXIT//
	setcolor(WHITE);
	settextstyle(1, 0, 1);
	outtextxy(595, 388, "E[X]IT");
}

void home_opt()
{
	char opt;
	opt = getche();
	if (!isalpha(opt))
		tolower(opt);
	switch (opt)
	{
	case 'u':
		if (sign == 0)
			account_sign_up();
		break;
	case 'i':
		if (sign == 0)
			account_sign_in();
		break;
	case 'o':
		if (sign == 1)
		{
			account_sign_inout();
			home();
		}
		break;
	case '1':
		if (sign == 1)
			library();
		else
			sign_in_msg();
		break;
	case '2':
		about();
		break;
	case '3':
		account_edit();
		break;
	case 'x':
		exit(0);
		break;
	default:
		home();
		break;
	}
}
//END HOME FUNCTION DEFINATION//
void account_sign_up()
{

	int i, j;
	cleardevice();

	ifstream fin, fincr;
	ofstream foutcr;
	fincr.open("tac.data", ios::in | ios::binary);
	fincr.read((char *)&crac, sizeof(crac));
	if (crac == 9)
	{
		fincr.close();
		setbkcolor(YELLOW);
		setcolor(LIGHTRED);
		rectangle(0, 190, 640, 310);
		setfillstyle(1, LIGHTRED);
		floodfill(0 + 50, 190 + 5, LIGHTRED);

		setcolor(YELLOW);
		settextstyle(0, 0, 3);
		outtextxy(0, 235, "      No More Accounts");
		outtextxy(0, 275, "        Limit Reached");
		delay(1000);
		home();
	}

	setbkcolor(YELLOW);

	//INFO TEXT//
	setcolor(CYAN);
	settextstyle(0, 0, 2);
	outtextxy(40, 140, "Add an account and get");
	outtextxy(40, 160, "your own music library");

	setcolor(YELLOW);
	//HEADER//
	for (i = 5; i <= 600; i += 130)
	{

		circle(7 + i, 20, 25);
		setfillstyle(5, LIGHTRED);
		floodfill(7 + i, 20, YELLOW);

		circle(30 + i, 75, 28);
		setfillstyle(1, CYAN);
		floodfill(30 + i, 75, YELLOW);

		circle(70 + i, 15, 35);
		setfillstyle(1, LIGHTGREEN);
		floodfill(70 + i, 15, YELLOW);

		circle(90 + i, 75, 25);
		setfillstyle(5, LIGHTCYAN);
		floodfill(90 + i, 75, YELLOW);
	}

	//FOOTER//
	for (i = 5; i <= 600; i += 130)
	{
		int j = 385;

		circle(7 + i, 20 + j, 25);
		setfillstyle(5, LIGHTRED);
		floodfill(7 + i, 20 + j, YELLOW);

		circle(30 + i, 75 + j, 28);
		setfillstyle(1, CYAN);
		floodfill(30 + i, 75 + j, YELLOW);

		circle(70 + i, 15 + j, 35);
		setfillstyle(1, LIGHTGREEN);
		floodfill(70 + i, 15 + j, YELLOW);

		circle(90 + i, 75 + j, 25);
		setfillstyle(5, LIGHTCYAN);
		floodfill(90 + i, 75 + j, YELLOW);
	}

	//BOX//
	for (i = 0, j = 0; i < 5; i++, j++)
	{
		if (i < 4)
		{
			setcolor(CYAN);
			rectangle(410 + i, 120 + j, 590 + i, 320 + j);
			setfillstyle(1, YELLOW);
			floodfill(410 + 50 + i, 120 + 5 + j, CYAN);
		}
		else
		{
			setcolor(12);
			rectangle(410 + i, 120 + j, 590 + i, 320 + j);
			setfillstyle(1, YELLOW);
			floodfill(410 + 50 + i, 120 + 5 + j, LIGHTRED);
		}
	}

	//COLUMN//
	setcolor(CYAN);
	//NAME//
	rectangle(425, 175, 585, 195);
	setfillstyle(1, WHITE);
	floodfill(425 + 50, 175 + 5, CYAN);
	//PASSWORD//
	rectangle(425, 220, 585, 240);
	setfillstyle(1, WHITE);
	floodfill(425 + 50, 220 + 5, CYAN);
	//SIGN UP//
	rectangle(452, 270, 560, 295);
	setfillstyle(1, CYAN);
	floodfill(452 + 50, 270 + 5, CYAN);

	//SIGN UP COLUMN TEXT//
	setcolor(LIGHTRED);
	settextstyle(10, 0, 1);
	outtextxy(449, 120, "SIGN UP");
	setcolor(CYAN);
	settextstyle(6, 0, 1);
	outtextxy(428, 170, "NAME:");
	outtextxy(428, 215, "PASS:");
	setcolor(WHITE);
	settextstyle(1, 0, 1);
	outtextxy(460, 270, " SUBMIT");
	//END SIGN UP COLUMN TEXT//

	gotoxy(61, 12);
	gets(account.name);
	gotoxy(61, 15);
	gets(account.pass);
	if (strlen(account.name) < 5 || strlen(account.pass) < 5)
	{
		cleardevice();
		setbkcolor(YELLOW);
		setcolor(LIGHTRED);
		rectangle(0, 190, 640, 290);
		setfillstyle(1, LIGHTRED);
		floodfill(0 + 50, 190 + 5, LIGHTRED);

		setcolor(YELLOW);
		settextstyle(0, 0, 3);
		outtextxy(0, 235, " NAME/PASS MUST HAVE  5-14 CHARACTERS");
		delay(1000);
		home();
	}
	int found = 0;

	fin.open("manage.lis", ios::in | ios::binary);

	for (i = 0; i < 10; i++)
	{
		fin.read((char *)&list[i], sizeof(list[i]));
		if (!strcmp(list[i].name, account.name))
		{
			found = 1;
			cleardevice();
			setbkcolor(YELLOW);
			setcolor(LIGHTRED);
			rectangle(0, 190, 640, 290);
			setfillstyle(1, LIGHTRED);
			floodfill(0 + 50, 190 + 5, LIGHTRED);

			setcolor(YELLOW);
			settextstyle(0, 0, 3);
			outtextxy(0, 235, "      NAME ALREADY TAKEN");
			delay(1000);
			home();
		}
	}
	fin.close();
	if (found == 0)

		fincr.open("tac.data", ios::in | ios::binary);
	fincr.read((char *)&crac, sizeof(crac));
	fincr.close();

	strcpy(list[crac].name, account.name);
	strcpy(list[crac].pass, account.pass);
	ofstream fout;
	fout.open("manage.lis", ios::out | ios::binary);
	fout.write((char *)&list, sizeof(list));
	fout.close();
	crac++;
	foutcr.open("tac.data", ios::out | ios::binary);
	foutcr.write((char *)&crac, sizeof(crac));
	foutcr.close();

	fout.open(account.name, ios::out | ios::binary);
	fout.write((char *)&account, sizeof(account));
	fout.close();

	cleardevice();
	setbkcolor(YELLOW);
	setcolor(LIGHTRED);
	rectangle(0, 190, 640, 290);
	setfillstyle(1, LIGHTRED);
	floodfill(0 + 50, 190 + 5, LIGHTRED);

	setcolor(YELLOW);
	settextstyle(0, 0, 3);
	outtextxy(0, 235, "   Your account is added");
	delay(1000);
	home();
};

void account_sign_in()
{
	int found = 0, i;
	gotoxy(61, 12);
	gets(account.name);
	gotoxy(61, 15);
	gets(account.pass);
	if (strlen(account.name) < 5 || strlen(account.pass) < 5)
	{
		cleardevice();
		setbkcolor(YELLOW);
		setcolor(LIGHTRED);
		rectangle(0, 190, 640, 290);
		setfillstyle(1, LIGHTRED);
		floodfill(0 + 50, 190 + 5, LIGHTRED);

		setcolor(YELLOW);
		settextstyle(0, 0, 3);
		outtextxy(0, 235, " NAME/PASS MUST HAVE  5-14 CHARACTERS");
		delay(1000);
		home();
	}

	ifstream fin;
	fin.open("manage.lis", ios::in | ios::binary);
	for (i = 0; i < 100; i++)
	{
		fin.read((char *)&list[i], sizeof(list[i]));
		if (!strcmp(list[i].name, account.name) && !strcmp(list[i].pass, account.pass))
		{
			found = 1;
			ifstream finac(account.name, ios::in | ios::binary);
			finac.read((char *)&account, sizeof(account));

			finac.close();
			account_sign_inout();
			sign = 1;
			break;
		}
	}
	fin.close();
	if (found == 1)
	{

		cleardevice();
		setbkcolor(LIGHTRED);
		setcolor(YELLOW);
		rectangle(150, 210, 500, 270);
		setfillstyle(1, YELLOW);
		floodfill(150 + 50, 210 + 5, YELLOW);

		setcolor(CYAN);
		settextstyle(0, 0, 3);
		outtextxy(170, 235, " SIGNING IN");
		delay(1000);
		home();
	}

	else
	{
		account_sign_inout();
		cleardevice();
		setbkcolor(LIGHTRED);
		setcolor(YELLOW);
		rectangle(60, 210, 590, 270);
		setfillstyle(1, YELLOW);
		floodfill(150 + 50, 210 + 5, YELLOW);

		setcolor(CYAN);
		settextstyle(0, 0, 3);
		outtextxy(75, 235, "NAME/PASS NOT MATCHED");
		delay(1000);
		home();
	}
}

void account_sign_inout()
{
	cleardevice();
	setbkcolor(LIGHTRED);

	//SIGN OUT//
	if (sign == 1)
	{
		sign = 0;
		setcolor(YELLOW);
		rectangle(150, 210, 500, 270);
		setfillstyle(1, YELLOW);
		floodfill(150 + 50, 210 + 5, YELLOW);

		setcolor(CYAN);
		settextstyle(0, 0, 3);
		outtextxy(170, 235, " SIGNING OUT");
		delay(1000);
		home();
	}
	//SIGN IN//
	else
	{
		cleardevice();
		setcolor(YELLOW);
		rectangle(150, 210, 500, 270);
		setfillstyle(1, YELLOW);
		floodfill(150 + 50, 210 + 5, YELLOW);

		setcolor(CYAN);
		settextstyle(0, 0, 3);
		outtextxy(160, 235, "   CHECKING");
		delay(1000);
	}
}

void sign_in_msg()
{
	cleardevice();
	setbkcolor(LIGHTRED);
	setcolor(YELLOW);
	rectangle(150, 210, 500, 270);
	setfillstyle(1, YELLOW);
	floodfill(150 + 50, 210 + 5, YELLOW);

	setcolor(CYAN);
	settextstyle(0, 0, 3);
	outtextxy(160, 235, "SIGN IN FIRST!");
	delay(1000);
	home();
}

void library()
{
	int i, j;
	char opt;

	cleardevice();
	setbkcolor(WHITE);
	setcolor(LIGHTRED);
	rectangle(0, 0, 640, 50);
	setfillstyle(1, LIGHTRED);
	floodfill(0 + 50, 0 + 5, LIGHTRED);

	setcolor(WHITE);
	settextstyle(0, 0, 4);
	outtextxy(60, 5, "Your Music List");

	setcolor(CYAN);
	rectangle(0, 450, 640, 480);
	setfillstyle(1, CYAN);
	floodfill(0 + 50, 450 + 5, CYAN);

	setcolor(WHITE);
	settextstyle(0, 0, 2);
	outtextxy(80, 455, "[H]OME          E[X]IT");

	settextstyle(0, 0, 1);
	for (i = 0; i < 50; i++)
	{
		strcpy(mulist[i].name, "");
	}
	ifstream fin("managemu.lis", ios::in | ios::binary);
	fin.read((char *)&mulist, sizeof(mulist));
	int k = 0;

	for (i = 0; i < 375; i += 75)
	{
		for (j = 0; j < 400; j += 40)
		{
			if (k >= 50)
			{
				break;
			}
			setcolor(GREEN);

			if (!strcmp(account.name, mulist[k].account))
			{
				outtextxy(30 + i, 70 + j, mulist[k].name);
			}
			else
				j -= 40;

			k++;
		}
		if (k >= 50)
		{
			break;
		}
	}
	fin.close();

	//BOX//
	for (i = 0, j = 0; i < 5; i++, j++)
	{
		if (i < 4)
		{
			setcolor(YELLOW);
			rectangle(410 + i, 120 + j, 590 + i, 320 + j);
			setfillstyle(1, LIGHTRED);
			floodfill(410 + 50 + i, 120 + 5 + j, YELLOW);
		}
		else
		{
			setcolor(CYAN);
			rectangle(410 + i, 120 + j, 590 + i, 320 + j);
			setfillstyle(1, LIGHTRED);
			floodfill(410 + 50 + i, 120 + 5 + j, CYAN);
		}
	}

	//COLUMN//
	setcolor(CYAN);
	//PASSWORD//
	rectangle(425, 130, 585, 150);
	setfillstyle(1, WHITE);
	floodfill(425 + 50, 130 + 5, CYAN);
	//SEARCH BOX//
	rectangle(452, 170, 560, 195);
	rectangle(452, 220, 560, 245);
	rectangle(452, 270, 560, 295);
	setfillstyle(1, CYAN);
	floodfill(452 + 50, 170 + 5, CYAN);
	floodfill(452 + 50, 220 + 5, CYAN);
	floodfill(452 + 50, 270 + 5, CYAN);

	//SIGN UP COLUMN TEXT//
	setcolor(CYAN);
	settextstyle(6, 0, 1);
	outtextxy(428, 125, "NAME:");
	setcolor(WHITE);
	settextstyle(1, 0, 1);
	outtextxy(460, 170, "[A]DD NEW");
	outtextxy(460, 220, " [D]ELETE");
	outtextxy(460, 270, "   [P]LAY");
	//END SIGN UP COLUMN TEXT//

	opt = getche();
	tolower(opt);
	switch (opt)
	{
	case 'a':
		library_add_new();
		break;

	case 'd':
		library_delete();
		break;
	case 'p':
		library_play();
		break;

	case 'h':
		home();
		break;
	case 'x':
		exit(0);
	default:
		library();
		break;
	}
}

void library_add_new()
{
	int i;
	char n;

	cleardevice();
	setbkcolor(LIGHTRED);
	setcolor(YELLOW);
	//FOOTER//
	for (i = 5; i <= 600; i += 130)
	{
		int j = 385;

		circle(7 + i, 20 + j, 25);
		setfillstyle(5, YELLOW);
		floodfill(7 + i, 20 + j, YELLOW);

		circle(30 + i, 75 + j, 28);
		setfillstyle(1, CYAN);
		floodfill(30 + i, 75 + j, YELLOW);

		circle(70 + i, 15 + j, 35);
		setfillstyle(1, LIGHTGREEN);
		floodfill(70 + i, 15 + j, YELLOW);

		circle(90 + i, 75 + j, 25);
		setfillstyle(5, LIGHTCYAN);
		floodfill(90 + i, 75 + j, YELLOW);
	}

	textcolor(YELLOW);

	for (i = 0; i < 500; i++)
	{
		music.script[i] = ' ';
	}

	for (i = 0; i < 500; i++)
	{
		n = getche();
		if (((int)n >= 65 && (int)n <= 90) || ((int)n >= 97 && (int)n <= 122) || n == '0' || n == '1')
		{
			if (n == '0')
				break;

			music.script[i] = n;

			library_sound_play(music.script[i]);
			library_disco();

			//DISCO TEXT//
			setcolor(CYAN);
			settextstyle(0, 0, 2);
			outtextxy(525, 4, "SAVE[0]");
			//END DISCO TEXT//

			delay(100);
			nosound();
		}
		else
			i--;
	}

	if (i == 499)
	{
		cleardevice();
		setbkcolor(YELLOW);
		setcolor(LIGHTRED);
		rectangle(0, 190, 640, 290);
		setfillstyle(1, LIGHTRED);
		floodfill(0 + 50, 190 + 5, LIGHTRED);

		setcolor(YELLOW);
		settextstyle(0, 0, 3);
		outtextxy(0, 235, "     RECORD LIMIT REACHED!");

		delay(1000);
	}
	library_save();
}

void library_disco()
{
	clrscr();

	for (int i = 70; i <= 570; i += 100)
	{
		for (int j = 50; j <= 350; j += 100)
		{
			setcolor(LIGHTRED);
			circle(i, j, random(35 - 20 + 1) + 20);
			setfillstyle(4, YELLOW);
			floodfill(i, j, LIGHTRED);
		}
	}
}

void library_sound_play(char n)
{
	switch (n)
	{
	case 'z':
		sound(27.5000);
		break;
	case 'x':
		sound(32.7032);
		break;
	case 'c':
		sound(38.8909);
		break;
	case 'v':
		sound(46.2493);
		break;
	case 'b':
		sound(55.0000);
		break;
	case 'n':
		sound(61.7354);
		break;
	case 'm':
		sound(73.4162);
		break;
	case 'a':
		sound(87.3071);
		break;
	case 's':
		sound(103.826);
		break;
	case 'd':
		sound(123.471);
		break;
	case 'f':
		sound(146.8325);
		break;
	case 'g':
		sound(174.6145);
		break;
	case 'h':
		sound(207.6525);
		break;
	case 'j':
		sound(246.9425);
		break;
	case 'k':
		sound(293.6655);
		break;
	case 'l':
		sound(359.2285);
		break;
	case 'q':
		sound(415.3055);
		break;
	case 'w':
		sound(493.8835);
		break;
	case 'e':
		sound(587.3305);
		break;
	case 'r':
		sound(698.4565);
		break;
	case 't':
		sound(830.6095);
		break;
	case 'y':
		sound(987.7675);
		break;
	case 'u':
		sound(1174.6650);
		break;
	case 'i':
		sound(1396.9150);
		break;
	case 'o':
		sound(1567.9850);
		break;
	case 'p':
		sound(1864.6650);
		break;
	case '1':
		break;
	}
}

void library_save()
{
	char opt, csname[15];
	cleardevice();
	setbkcolor(YELLOW);

	setcolor(LIGHTRED);
	circle(320, 0, 350);
	setfillstyle(1, LIGHTRED);
	floodfill(320, 0, LIGHTRED);

	//TITLE//
	setcolor(WHITE);
	settextstyle(0, 0, 4);
	outtextxy(45, 5, "THE MUSIC LIBRARY");

	setcolor(CYAN);
	settextstyle(0, 0, 2);
	outtextxy(225, 82, "Name:");

	gotoxy(45, 6);

	for (int i = 0; i < 50; i++)
	{
		strcpy(mulist[i].name, "");
	}
	ifstream fincr, fin;
	ofstream foutcr, fout;

	fincr.open("tmu.dat", ios::in | ios::binary);
	fincr.read((char *)&crs, sizeof(crs));
	fincr.close();

	fin.open("managemu.lis", ios::in | ios::binary);

	fin.read((char *)&mulist, sizeof(mulist));

	fin.close();

	gets(mulist[crs].name);
	if (strlen(mulist[crs].name) >= 10)
	{
		cleardevice();
		setbkcolor(YELLOW);
		setcolor(LIGHTRED);
		rectangle(0, 190, 640, 290);
		setfillstyle(1, LIGHTRED);
		floodfill(0 + 50, 190 + 5, LIGHTRED);

		setcolor(YELLOW);
		settextstyle(0, 0, 3);
		outtextxy(0, 235, " NAME CAN HAVE MAX 10 CHARACTERS");
		delay(1000);
		library_save();
	}

	fout.open("managemu.lis", ios::out | ios::binary);
	strcpy(mulist[crs].account, account.name);
	fout.write((char *)&mulist, sizeof(mulist));
	fout.close();

	fout.open(mulist[crs].name, ios::out | ios::binary);
	fout.write((char *)&music, sizeof(music));
	fout.close();

	foutcr.open("tmu.dat", ios::out | ios::binary);
	crs++;
	foutcr.write((char *)&crs, sizeof(crs));

	foutcr.close();

	outtextxy(10, 400, "  The song is added to LIBRARY PLAY");

	rectangle(0, 450, 640, 480);
	setfillstyle(1, CYAN);
	floodfill(0 + 50, 450 + 5, CYAN);

	setcolor(WHITE);
	outtextxy(0, 453, "[L]IBRARY            [H]OME");

	opt = getche();
	tolower(opt);
	switch (opt)
	{

	case 'l':
		library();
		break;
	case 'h':
		home();
		break;

	default:
		opt = getche();
		break;
	}
}

void library_delete()
{
	int j = 0, n = 0, found = 0;
	char sname[10];
	gotoxy(61, 9);
	gets(sname);

	settextstyle(0, 0, 1);
	ifstream fin("managemu.lis", ios::in | ios::binary);
	fin.read((char *)&mulist, sizeof(mulist));
	fin.close();

	for (n = 0; n <= 50; n++)
	{

		if (!strcmp(mulist[n].name, sname))
		{
			found = 1;
			break;
		}
	}

	if (found == 0)
	{
		cleardevice();
		setbkcolor(LIGHTRED);
		setcolor(YELLOW);
		rectangle(60, 210, 590, 270);
		setfillstyle(1, YELLOW);
		floodfill(150 + 50, 210 + 5, YELLOW);

		setcolor(CYAN);
		settextstyle(0, 0, 3);
		outtextxy(75, 235, "Music Name Is Wrong");
		delay(1000);
		library();
	}

	fstream fiocr("tmu.dat", ios::in | ios::out | ios::binary);
	fiocr.read((char *)&crs, sizeof(crs));
	for (n = 0; n <= 50; n++)
	{
		if (!strcmp(mulist[n].name, sname))
		{
			remove(sname);
			for (j = n + 1; j <= 51; j++)
			{
				mulist[j - 1] = mulist[j];
			}
			crs--;
			fiocr.write((char *)&crs, sizeof(crs));

			n--;
		}
	}
	fiocr.close();
	ofstream fout("managemu.lis", ios::out | ios::binary);
	fout.write((char *)&mulist, sizeof(mulist));

	fout.close();

	cleardevice();
	setbkcolor(LIGHTRED);
	setcolor(YELLOW);
	rectangle(60, 210, 590, 270);
	setfillstyle(1, YELLOW);
	floodfill(150 + 50, 210 + 5, YELLOW);
	setcolor(CYAN);
	settextstyle(0, 0, 3);

	outtextxy(75, 235, "DELETING YOUR MUSIC");
	delay(1000);

	cleardevice();
	setbkcolor(LIGHTRED);
	setcolor(YELLOW);
	rectangle(60, 210, 590, 270);
	setfillstyle(1, YELLOW);
	floodfill(150 + 50, 210 + 5, YELLOW);
	setcolor(CYAN);
	settextstyle(0, 0, 3);
	outtextxy(75, 235, "    MUSIC  DELETED");
	delay(1000);

	library();
};

void library_play()
{
	int i;
	char sname[10], n;
	for (i = 0; i < 500; i++)
	{
		music.script[i] = ' ';
	}
	gotoxy(61, 9);

	gets(sname);

	ifstream fin(sname, ios::in | ios::binary);
	if (!fin)
	{
		fin.close();
		cleardevice();
		setbkcolor(LIGHTRED);
		setcolor(YELLOW);
		rectangle(60, 210, 590, 270);
		setfillstyle(1, YELLOW);
		floodfill(150 + 50, 210 + 5, YELLOW);

		setcolor(CYAN);
		settextstyle(0, 0, 3);
		outtextxy(75, 235, "Music Name Is Wrong");
		delay(1000);
		library();
	}
	fin.read((char *)&music, sizeof(music));
	fin.close();

	cleardevice();
	setbkcolor(LIGHTRED);
	setcolor(YELLOW);
	//FOOTER//
	for (i = 5; i <= 600; i += 130)
	{
		int j = 385;

		circle(7 + i, 20 + j, 25);
		setfillstyle(5, YELLOW);
		floodfill(7 + i, 20 + j, YELLOW);

		circle(30 + i, 75 + j, 28);
		setfillstyle(1, CYAN);
		floodfill(30 + i, 75 + j, YELLOW);

		circle(70 + i, 15 + j, 35);
		setfillstyle(1, LIGHTGREEN);
		floodfill(70 + i, 15 + j, YELLOW);

		circle(90 + i, 75 + j, 25);
		setfillstyle(5, LIGHTCYAN);
		floodfill(90 + i, 75 + j, YELLOW);
	}

	textcolor(YELLOW);

	for (i = 0; i < 500; i++)
	{
		n = music.script[i];
		if (((int)n >= 65 && (int)n <= 90) || ((int)n >= 97 && (int)n <= 122) || n == '0' || n == '1')
		{
			if (n == '0')
				break;

			library_sound_play(music.script[i]);
			library_disco();
			delay(100);
			nosound();
		}
	}

	library();
}

void account_edit()
{
	char opt;
	cleardevice();
	setbkcolor(WHITE);

	setcolor(LIGHTRED);
	circle(315, 0, 350);
	setfillstyle(1, LIGHTRED);
	floodfill(315, 0, LIGHTRED);

	//TITLE//
	setcolor(WHITE);
	settextstyle(0, 0, 4);
	outtextxy(60, 5, "EDIT YOU ACCOUNT");

	setcolor(CYAN);
	settextstyle(0, 0, 2);
	outtextxy(30, 92, "[1] Delete An Account");
	outtextxy(30, 122, "[2] Change Pass Of An Account");
	outtextxy(30, 152, "[3] Reset All Data");
	outtextxy(30, 182, "[4] UNINSTALL");

	rectangle(0, 450, 640, 480);
	setfillstyle(1, CYAN);
	floodfill(0 + 50, 450 + 5, CYAN);

	setcolor(WHITE);
	outtextxy(0, 455, "[H]OME                            E[X]IT");

	opt = getche();
	tolower(opt);
	switch (opt)
	{
	case '1':
		account_del();
		break;
	case '2':
		account_pch();
		break;
	case '3':
		reset_data();
		home();
		break;
	case '4':
		uninstall();
		break;
	case 'h':
		home();
		break;
	case 'x':
		exit(0);
		break;
	}
}

void account_del()
{
	int i, j, found = 0;
	char name[20], pass[20];
	cleardevice();
	setbkcolor(YELLOW);

	//INFO TEXT//
	setcolor(CYAN);
	settextstyle(0, 0, 2);
	outtextxy(10, 140, "  Your account will be ");
	outtextxy(10, 160, "permanently deleted and ");
	outtextxy(10, 180, "  data will be erased");

	setcolor(YELLOW);
	//HEADER//
	for (i = 5; i <= 600; i += 130)
	{

		circle(7 + i, 20, 25);
		setfillstyle(5, LIGHTRED);
		floodfill(7 + i, 20, YELLOW);

		circle(30 + i, 75, 28);
		setfillstyle(1, CYAN);
		floodfill(30 + i, 75, YELLOW);

		circle(70 + i, 15, 35);
		setfillstyle(1, LIGHTGREEN);
		floodfill(70 + i, 15, YELLOW);

		circle(90 + i, 75, 25);
		setfillstyle(5, LIGHTCYAN);
		floodfill(90 + i, 75, YELLOW);
	}

	//FOOTER//
	for (i = 5; i <= 600; i += 130)
	{
		int j = 385;

		circle(7 + i, 20 + j, 25);
		setfillstyle(5, LIGHTRED);
		floodfill(7 + i, 20 + j, YELLOW);

		circle(30 + i, 75 + j, 28);
		setfillstyle(1, CYAN);
		floodfill(30 + i, 75 + j, YELLOW);

		circle(70 + i, 15 + j, 35);
		setfillstyle(1, LIGHTGREEN);
		floodfill(70 + i, 15 + j, YELLOW);

		circle(90 + i, 75 + j, 25);
		setfillstyle(5, LIGHTCYAN);
		floodfill(90 + i, 75 + j, YELLOW);
	}

	//BOX//
	for (i = 0, j = 0; i < 5; i++, j++)
	{
		if (i < 4)
		{
			setcolor(CYAN);
			rectangle(410 + i, 120 + j, 590 + i, 320 + j);
			setfillstyle(1, YELLOW);
			floodfill(410 + 50 + i, 120 + 5 + j, CYAN);
		}
		else
		{
			setcolor(12);
			rectangle(410 + i, 120 + j, 590 + i, 320 + j);
			setfillstyle(1, YELLOW);
			floodfill(410 + 50 + i, 120 + 5 + j, LIGHTRED);
		}
	}

	//COLUMN//
	setcolor(CYAN);
	//NAME//
	rectangle(425, 175, 585, 195);
	setfillstyle(1, WHITE);
	floodfill(425 + 50, 175 + 5, CYAN);
	//PASSWORD//
	rectangle(425, 220, 585, 240);
	setfillstyle(1, WHITE);
	floodfill(425 + 50, 220 + 5, CYAN);
	//SIGN UP//
	rectangle(452, 270, 560, 295);
	setfillstyle(1, CYAN);
	floodfill(452 + 50, 270 + 5, CYAN);

	//SIGN UP COLUMN TEXT//
	setcolor(LIGHTRED);
	settextstyle(10, 0, 1);
	outtextxy(449, 120, "DETAILS");
	setcolor(CYAN);
	settextstyle(6, 0, 1);
	outtextxy(428, 170, "NAME:");
	outtextxy(428, 215, "PASS:");
	setcolor(WHITE);
	settextstyle(1, 0, 1);
	outtextxy(460, 270, " DELETE");
	//END SIGN UP COLUMN TEXT//

	gotoxy(61, 12);
	gets(name);
	gotoxy(61, 15);
	gets(pass);
	if (strlen(name) < 5 || strlen(pass) < 5)
	{
		cleardevice();
		setbkcolor(YELLOW);
		setcolor(LIGHTRED);
		rectangle(0, 190, 640, 290);
		setfillstyle(1, LIGHTRED);
		floodfill(0 + 50, 190 + 5, LIGHTRED);

		setcolor(YELLOW);
		settextstyle(0, 0, 3);
		outtextxy(0, 235, " NAME/PASS MUST HAVE  6-14 CHARACTERS");
		delay(1000);
		account_del();
	}

	ifstream fin;
	fin.open("manage.lis", ios::in | ios::binary);
	fin.read((char *)&list, sizeof(list));
	fin.close();
	for (i = 0; i < 100; i++)
	{
		if ((strcmp(list[i].name, name) == 0) && (strcmp(list[i].pass, pass) == 0))
		{
			found = 1;
			break;
		}
	}

	if (found == 0)
	{
		cleardevice();
		setbkcolor(LIGHTRED);
		setcolor(YELLOW);
		rectangle(60, 210, 590, 270);
		setfillstyle(1, YELLOW);
		floodfill(150 + 50, 210 + 5, YELLOW);

		setcolor(CYAN);
		settextstyle(0, 0, 3);
		outtextxy(75, 235, "NAME/PASS NOT MATCHED");
		delay(1000);
		account_edit();
	}

	for (j = i + 1; j < 10; j++)
		list[j - 1] = list[j];

	ofstream fout;

	fout.open("manage.lis", ios::out | ios::binary);
	fout.write((char *)&list, sizeof(list));
	fout.close();

	fin.open("tac.dat", ios::in | ios::binary);
	fin.read((char *)&crac, sizeof(crac));
	fin.close();

	crac--;

	fout.open("tac.dat", ios::out | ios::binary);
	fout.write((char *)&crac, sizeof(crac));
	fout.close();

	int l;

	fin.open("managemu.lis", ios::in | ios::binary);
	fin.read((char *)&mulist, sizeof(mulist));
	fin.close();
	fstream fiocr;
	fiocr.open("tmu.dat", ios::in | ios::out | ios::binary);
	fiocr.read((char *)&crs, sizeof(crs));
	for (i = 0; i < 50; i++)
	{
		if (!strcmp(name, mulist[i].account))
		{
			remove(mulist[i].name);
			for (int j = i + 1; j <= 51; j++)
			{
				mulist[j - 1] = mulist[j];
			}
			crs--;
			fiocr.write((char *)&crs, sizeof(crs));
			i--;
		}
	}
	fiocr.close();
	remove(name);
	fout.open("managemu.lis", ios::out | ios::binary);
	fout.write((char *)&mulist, sizeof(mulist));
	fout.close();

	//SIGN OUT MESSAGE//
	if (sign == 1)
	{
		cleardevice();
		setbkcolor(LIGHTRED);

		sign = 0;

		setcolor(YELLOW);
		rectangle(150, 210, 500, 270);
		setfillstyle(1, YELLOW);
		floodfill(150 + 50, 210 + 5, YELLOW);

		setcolor(CYAN);
		settextstyle(0, 0, 3);
		outtextxy(170, 235, " SIGNING OUT");
		delay(1000);
	}
	//END SIGN OUT//

	//DISPLAY MESSAGE//
	cleardevice();
	setbkcolor(LIGHTRED);
	setcolor(YELLOW);
	rectangle(0, 210, 640, 270);
	setfillstyle(1, YELLOW);
	floodfill(0 + 50, 210 + 5, YELLOW);

	setcolor(CYAN);
	settextstyle(0, 0, 3);
	outtextxy(50, 235, "Your account is deleted");
	delay(1000);
	//END DISPLAY MESSAGE//
	home();
}

void account_pch()
{
	//VARIABLES//
	int i, j, found = 0;
	char name[20], pass[20], new_pass[20];
	ofstream fout;
	ifstream fin;

	cleardevice();
	setbkcolor(YELLOW);

	setcolor(YELLOW);
	//HEADER//
	for (i = 5; i <= 600; i += 130)
	{

		circle(7 + i, 20, 25);
		setfillstyle(5, LIGHTRED);
		floodfill(7 + i, 20, YELLOW);

		circle(30 + i, 75, 28);
		setfillstyle(1, CYAN);
		floodfill(30 + i, 75, YELLOW);

		circle(70 + i, 15, 35);
		setfillstyle(1, LIGHTGREEN);
		floodfill(70 + i, 15, YELLOW);

		circle(90 + i, 75, 25);
		setfillstyle(5, LIGHTCYAN);
		floodfill(90 + i, 75, YELLOW);
	}

	//FOOTER//
	for (i = 5; i <= 600; i += 130)
	{
		int j = 385;

		circle(7 + i, 20 + j, 25);
		setfillstyle(5, LIGHTRED);
		floodfill(7 + i, 20 + j, YELLOW);

		circle(30 + i, 75 + j, 28);
		setfillstyle(1, CYAN);
		floodfill(30 + i, 75 + j, YELLOW);

		circle(70 + i, 15 + j, 35);
		setfillstyle(1, LIGHTGREEN);
		floodfill(70 + i, 15 + j, YELLOW);

		circle(90 + i, 75 + j, 25);
		setfillstyle(5, LIGHTCYAN);
		floodfill(90 + i, 75 + j, YELLOW);
	}

	//BOX//
	for (i = 0, j = 0; i < 5; i++, j++)
	{
		if (i < 4)
		{
			setcolor(CYAN);
			rectangle(410 + i, 120 + j, 590 + i, 320 + j);
			setfillstyle(1, YELLOW);
			floodfill(410 + 50 + i, 120 + 5 + j, CYAN);
		}
		else
		{
			setcolor(12);
			rectangle(410 + i, 120 + j, 590 + i, 320 + j);
			setfillstyle(1, YELLOW);
			floodfill(410 + 50 + i, 120 + 5 + j, LIGHTRED);
		}
	}

	//COLUMN//
	setcolor(CYAN);
	//NAME//
	rectangle(425, 175, 585, 195);
	setfillstyle(1, WHITE);
	floodfill(425 + 50, 175 + 5, CYAN);
	//PASSWORD//
	rectangle(425, 220, 585, 240);
	setfillstyle(1, WHITE);
	floodfill(425 + 50, 220 + 5, CYAN);
	//NEW PASSWORD//
	rectangle(425, 268, 585, 288);
	setfillstyle(1, WHITE);
	floodfill(425 + 50, 268 + 5, CYAN);

	//SIGN UP COLUMN TEXT//
	setcolor(LIGHTRED);
	settextstyle(10, 0, 1);
	outtextxy(449, 120, "DETAILS");
	setcolor(CYAN);
	settextstyle(6, 0, 1);
	outtextxy(428, 170, "NAME:");
	outtextxy(428, 215, "PASS:");
	outtextxy(428, 263, "NEW PASS:");

	//END SIGN UP COLUMN TEXT//

	gotoxy(61, 12);
	gets(name);
	gotoxy(61, 15);
	gets(pass);
	gotoxy(66, 18);
	gets(new_pass);

	//ACCOUNT LIST IN MEMORY//
	fin.open("manage.lis", ios::in | ios::binary);
	fin.read((char *)&list, sizeof(list));
	fin.close();
	//ACCOUNT LIST TAKEN//

	//CHECK OLD PASS//
	for (i = 0; i <= 10; i++)
	{
		if ((strcmp(list[i].name, name) == 0) && (strcmp(list[i].pass, pass) == 0))
		{
			found = 1;
			break;
		}
	}

	if (found == 0)
	{
		//DISPLAY MESSAGE//
		cleardevice();
		setbkcolor(LIGHTRED);
		setcolor(YELLOW);
		rectangle(60, 210, 590, 270);
		setfillstyle(1, YELLOW);
		floodfill(150 + 50, 210 + 5, YELLOW);

		setcolor(CYAN);
		settextstyle(0, 0, 3);
		outtextxy(75, 235, "NAME/PASS NOT MATCHED");
		delay(1000);
		//END DISPLAY MESSAGE//
		account_edit();
	}
	//OLD PASS CHECKED//

	//CHECK NEW PASS//
	if (strlen(new_pass) < 5)
	{
		//DISPLAY MESSAGE//
		cleardevice();
		setbkcolor(YELLOW);
		setcolor(LIGHTRED);
		rectangle(0, 190, 640, 290);
		setfillstyle(1, LIGHTRED);
		floodfill(0 + 50, 190 + 5, LIGHTRED);

		setcolor(YELLOW);
		settextstyle(0, 0, 3);
		outtextxy(0, 235, " NEW PASS MUST HAVE  6-14 CHARACTERS");
		delay(1000);
		//END DISPLAY MESSAGE//
		account_edit();
	}
	//NEW PASS CHECKED//

	//PASS UPDATED IN MEMORY//
	strcpy(list[i].pass, new_pass);

	//ACCOUNT LIST UPDATE//
	fout.open("manage.lis", ios::out | ios::binary);
	fout.write((char *)&list, sizeof(list));
	fout.close();
	//UPDATED//

	//DISPLAY MESSAGE//
	cleardevice();
	setbkcolor(LIGHTRED);
	setcolor(YELLOW);
	rectangle(0, 210, 640, 270);
	setfillstyle(1, YELLOW);
	floodfill(0 + 50, 210 + 5, YELLOW);

	setcolor(CYAN);
	settextstyle(0, 0, 3);
	outtextxy(50, 235, "  Your pass is changed");
	delay(1000);
	//END DISPLAY MESSAGE//

	home();
}

void reset_data()
{
	//VARIABLES//
	char pass[20];
	ifstream fin;
	ofstream fout;

	cleardevice();
	setbkcolor(YELLOW);

	//TOP CIRCLE//
	setcolor(LIGHTRED);
	circle(320, 0, 350);
	setfillstyle(1, LIGHTRED);
	floodfill(320, 0, LIGHTRED);
	//END CIRCLE//

	//TITLE//
	setcolor(WHITE);
	settextstyle(0, 0, 4);
	outtextxy(45, 5, " ENTER ADMIN PASS");
	//END TITLE//

	//TEXT//
	setcolor(CYAN);
	settextstyle(0, 0, 2);
	outtextxy(225, 82, "Pass:");
	//END TEXT//

	gotoxy(45, 6);

	//INPUT PASS//
	gets(pass);

	//ADMIN DATA IN MEMORY//
	fin.open("admin.dat", ios::in | ios::binary);
	fin.read((char *)&admin_pass, sizeof(admin_pass));
	fin.close();
	//ADMIN DATA TAKEN//

	//CHECK PASS//
	if (strcmp(pass, admin_pass))
	{
		cleardevice();
		setbkcolor(YELLOW);
		setcolor(LIGHTRED);
		rectangle(0, 190, 640, 290);
		setfillstyle(1, LIGHTRED);
		floodfill(0 + 50, 190 + 5, LIGHTRED);

		setcolor(YELLOW);
		settextstyle(0, 0, 3);
		outtextxy(0, 235, " ADMIN PASS DID NOT MATCH");
		delay(1000);
		account_edit();
	}
	//END CHECK PASS//

	fin.open("manage.lis", ios::in | ios::binary);
	fin.read((char *)&list, sizeof(list));
	for (int i = 0; i < 10; i++)
	{
		remove(list[i].name);
	}
	fin.close();

	fin.open("managemu.lis", ios::in | ios::binary);
	fin.read((char *)&mulist, sizeof(list));
	for (i = 0; i < 10; i++)
	{
		remove(mulist[i].name);
	}
	fin.close();

	//DELETE FILE SYSTEM//
	remove("admin.dat");
	remove("manage.lis");
	remove("managemu.lis");
	remove("tac.dat");
	remove("tmu.dat");
	//END DELETE FILE//

	//RESET DATA IN MEMORY//
	for (i = 0; i < 10; i++)
	{
		strcpy(list[i].name, "");
		strcpy(list[i].pass, "");
	}
	strcpy(account.name, "");
	strcpy(account.pass, "");
	strcpy(admin_pass, "");
	//RESET COMPLETE//

	//SIGN OUT//
	if (sign == 1)
	{
		cleardevice();
		setbkcolor(LIGHTRED);

		sign = 0;

		setcolor(YELLOW);
		rectangle(150, 210, 500, 270);
		setfillstyle(1, YELLOW);
		floodfill(150 + 50, 210 + 5, YELLOW);

		setcolor(CYAN);
		settextstyle(0, 0, 3);
		outtextxy(170, 235, " SIGNING OUT");
		delay(1000);
	}
	//END DISPLAY MESSAGE//

	//DISPLAY MESSAGE//
	cleardevice();
	setbkcolor(YELLOW);
	setcolor(LIGHTRED);
	rectangle(0, 190, 640, 290);
	setfillstyle(1, LIGHTRED);
	floodfill(0 + 50, 190 + 5, LIGHTRED);

	setcolor(YELLOW);
	settextstyle(0, 0, 3);
	outtextxy(0, 235, "     RESETTING ALL DATA");
	delay(1000);

	//PROGRAM RESTART//
	main();
}

void uninstall()
{
	//VARIABLES//
	char pass[20];
	ifstream fin;
	ofstream fout;

	cleardevice();
	setbkcolor(YELLOW);

	//TOP CIRCLE//
	setcolor(LIGHTRED);
	circle(320, 0, 350);
	setfillstyle(1, LIGHTRED);
	floodfill(320, 0, LIGHTRED);
	//END CIRCLE//

	//TITLE//
	setcolor(WHITE);
	settextstyle(0, 0, 4);
	outtextxy(45, 5, " ENTER ADMIN PASS");
	//END TITLE//

	//TEXT//
	setcolor(CYAN);
	settextstyle(0, 0, 2);
	outtextxy(225, 82, "Pass:");
	//END TEXT//

	gotoxy(45, 6);

	//INPUT PASS//
	gets(pass);

	//ADMIN DATA IN MEMORY//
	fin.open("admin.dat", ios::in | ios::binary);
	fin.read((char *)&admin_pass, sizeof(admin_pass));
	fin.close();
	//ADMIN DATA TAKEN//

	//CHECK PASS//
	if (strcmp(pass, admin_pass))
	{
		cleardevice();
		setbkcolor(YELLOW);
		setcolor(LIGHTRED);
		rectangle(0, 190, 640, 290);
		setfillstyle(1, LIGHTRED);
		floodfill(0 + 50, 190 + 5, LIGHTRED);

		setcolor(YELLOW);
		settextstyle(0, 0, 3);
		outtextxy(0, 235, " ADMIN PASS DID NOT MATCH");
		delay(1000);
		account_edit();
	}
	//END CHECK PASS//

	fin.open("manage.lis", ios::in | ios::binary);
	fin.read((char *)&list, sizeof(list));
	for (int i = 0; i < 10; i++)
	{
		remove(list[i].name);
	}
	fin.close();

	fin.open("managemu.lis", ios::in | ios::binary);
	fin.read((char *)&mulist, sizeof(list));
	for (i = 0; i < 10; i++)
	{
		remove(mulist[i].name);
	}
	fin.close();

	//DELETE FILE SYSTEM//
	remove("admin.dat");
	remove("manage.lis");
	remove("managemu.lis");
	remove("tac.dat");
	remove("tmu.dat");
	//END DELETE FILE//
	chdir("\\TC\\BIN");
	rmdir("\\MUSIC");

	//RESET DATA IN MEMORY//
	for (i = 0; i < 10; i++)
	{
		strcpy(list[i].name, "");
		strcpy(list[i].pass, "");
	}
	strcpy(account.name, "");
	strcpy(account.pass, "");
	strcpy(admin_pass, "");
	//RESET COMPLETE//

	//SIGN OUT//
	if (sign == 1)
	{
		cleardevice();
		setbkcolor(LIGHTRED);

		sign = 0;

		setcolor(YELLOW);
		rectangle(150, 210, 500, 270);
		setfillstyle(1, YELLOW);
		floodfill(150 + 50, 210 + 5, YELLOW);

		setcolor(CYAN);
		settextstyle(0, 0, 3);
		outtextxy(170, 235, " SIGNING OUT");
		delay(1000);
	}
	//END DISPLAY MESSAGE//

	//DISPLAY MESSAGE//
	cleardevice();
	setbkcolor(YELLOW);
	setcolor(LIGHTRED);
	rectangle(0, 190, 640, 290);
	setfillstyle(1, LIGHTRED);
	floodfill(0 + 50, 190 + 5, LIGHTRED);

	setcolor(YELLOW);
	settextstyle(0, 0, 3);
	outtextxy(0, 235, "        UNISTALLING ");
	delay(1000);
	cleardevice();
	setbkcolor(YELLOW);
	setcolor(LIGHTRED);
	rectangle(0, 190, 640, 290);
	setfillstyle(1, LIGHTRED);
	floodfill(0 + 50, 190 + 5, LIGHTRED);

	setcolor(YELLOW);
	settextstyle(0, 0, 3);
	outtextxy(0, 235, "  UNINSTALL COMPLETE! ");
	delay(1000);
	//PROGRAM RESTART//
	exit(0);
}
