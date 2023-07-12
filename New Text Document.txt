#include <iostream>
#include <conio.h>
using namespace std;

void SetOurMat(char x[][80], int& cte)
{
	for (int r = 0; r < 24; r++)
	{
		for (int c = 0; c < 80; c++)
		{
			x[r][c] = ' ';
		}
	}

	x[0][0] = 'L';
	x[0][1] = 'E';
	x[0][2] = 'V';
	x[0][3] = 'E';
	x[0][4] = 'L';
	x[0][5] = ' ';
	x[0][6] = '2';

	x[1][0] = 'S';
	x[1][1] = 'C';
	x[1][2] = 'O';
	x[1][3] = 'R';
	x[1][4] = 'E';

	x[2][0] = 201;
	x[23][0] = 200;
	x[2][79] = 187;
	x[23][79] = 188;

	for (int r = 3; r < 23; r++)
	{
		x[r][0] = 186;
	}

	for (int r = 3; r < 23; r++)
	{
		x[r][79] = 186;
	}

	for (int c = 1; c < 79; c++)
	{
		x[2][c] = 205;
	}

	for (int c = 1; c < 79; c++)
	{
		x[23][c] = 205;
	}

	for (int c = 1; c < 74; c++)
	{
		x[16][c] = 240;
	}
	x[16][78] = 240;



	x[17][27] = '||';
	x[17][29] = '||';
	x[17][28] = 210;
	x[17][62] = '||';
	x[17][64] = '||';
	x[17][63] = 210;




	for (int c = 10; c < 79; c++)
	{
		x[10][c] = 240;
	}
	x[10][9] = 240;
	x[10][10] = 240;
	x[10][11] = 240;
	x[10][12] = 240;
	x[10][13] = 240;
	x[10][14] = 240;
	x[10][2] = 240;
	x[10][1] = 240;

	x[3][56] = 179;
	x[4][56] = 179;
	x[5][56] = 179;
	x[6][56] = 179;
	x[7][56] = 179;
	x[3][57] = 179;
	x[4][57] = 179;
	x[5][57] = 179;
	x[6][57] = 179;
	x[7][57] = 179;
	x[3][58] = 179;
	x[4][58] = 179;
	x[5][58] = 179;
	x[6][58] = 179;
	x[7][58] = 179;
	x[3][59] = 179;
	x[4][59] = 179;
	x[5][59] = 179;
	x[6][59] = 179;
	x[7][59] = 179;

	x[3][74] = 179;
	x[4][74] = 179;
	x[5][74] = 179;
	x[6][74] = 179;
	x[7][74] = 179;
	x[3][77] = 179;
	x[4][77] = 179;
	x[5][77] = 179;
	x[6][77] = 179;
	x[7][77] = 179;
	x[3][76] = 179;
	x[4][76] = 179;
	x[5][76] = 179;
	x[6][76] = 179;
	x[7][76] = 179;
	x[3][75] = 179;
	x[4][75] = 179;
	x[5][75] = 179;
	x[6][75] = 179;
	x[7][75] = 179;


	x[5][1] = 240;
	x[5][2] = 240;

	x[3][21] = '*';
	x[4][21] = '*';
	x[5][21] = '*';
	x[6][21] = '*';
	x[7][21] = '*';

	x[7][9] = 240;
	x[7][10] = 240;
	x[8][11] = 240;
	x[8][12] = 240;
	x[9][13] = 240;
	x[9][14] = 240;

	x[4][15] = '<';
	x[4][16] = 254;
	x[4][17] = 254;
	x[3][17] = 'n';
	x[5][17] = 'u';
	x[4][18] = '~';

	x[9][78] = '@';
	if (x[9][78] == '0' || x[9][78] == '\\' || x[9][78] == '||' || x[9][78] == '//')
	{
		cte++;
	}
}

void MoveHeroPosition(char x[][80], int& rH, int& cH, char Q, int& sw, int& cts, int& ctj, int& ss, int& a, int& ss2, int& a2, int& mulleft, int& aleft, int& mulright, int& aright, int& ex)
{
	if (Q == 'a')
	{
		if (x[rH + 1][cH - 2] == ' ' && x[rH + 2][cH - 2] == ' ')
		{
			cH--;
		}


	}
	if (cts > 0)
	{
		if (Q == 'w')
		{

			sw = 0;
			cts = 0;
		}
	}
	if (cts == 0)
	{
		if (Q == 's')
		{
			cts++;
			sw = 1;
		}
	}
	//x[rH + 2][cH + 1] = '\\';
	if (Q == 'd')
	{

		if (x[rH + 1][cH + 2] == ' ')
		{
			cH++;
		}
	}

	if (Q == 'g')
	{

		ss = 1;
		a = cH + 2;

	}
	if (Q == 'f')
	{
		ss2 = 1;
		a2 = cH - 2;

	}
	if (Q == 'z')
	{


	}
	if (Q == 'x')
	{
		ss = 1;
		mulright = 1;


	}
	if (x[rH + 3][cH + 1] == ' ' && x[rH + 3][cH] == ' ' && x[rH + 3][cH - 1] == ' ')
	{
		rH++;
	}
	if (Q == 'e')
	{
		rH--;
		cH++;
	}
	if (Q == 'q')
	{
		rH--;
		cH--;
	}
}

void death(char x[][80], int& rH, int& cH, int& rE, int& cE, int& ctd, int& cth)
{
	if (x[rH + 1][cH] == '/' || x[rH + 1][cH] == '\\' || x[rH][cH] == '|' || x[rH][cH] == '\\' || x[rH][cH] == '/' || x[rH + 1][cH + 1] == '/' || x[rH + 1][cH - 1] == '\\' || x[rH + 1][cH + 1] == '|' || x[rH + 1][cH - 1] == '|' || x[rH][cH] == 179 || x[rH + 1][cH + 1] == 179 || x[rH][cH] == '.' || x[rH][cH] == 233)
	{
		cth = 1;
	}



	if (x[rE + 1][cE - 2] == 'o')
	{
		ctd = 1;
	}

	//	x[rH][cH] = '0';
	//	x[rH + 1][cH] = '|';
	//	x[rH + 1][cH + 1] = '\\';
	//	x[rH + 1][cH - 1] = '//';
	//	x[rH + 2][cH + 1] = '\\';
	//	x[rH + 2][cH - 1] = '//';
}

void SetHero(char x[][80], int rH, int cH, int& sw, int& cts, int& ss, int& a, int& ss2, int& a2, int& cts2, int& mulright, int& mulleft, int& aright, int& aleft, int& cth)
{
	//---------Shoot going right---------------
	if (ss == 1)
	{
		if (cts == 0)
		{
			a = cH + 2;
		}

		x[rH + 1][a + 2] = 'o';
		a++;
		cts++;


		if (cts > 5 && mulright == 1)
		{
			if (cts == 5)
			{
				aright = cH + 5;
			}
			x[10][16] = 'p';
			x[rH + 1][aright + 2] = '=';
			aright++;
			cts++;
		}




		if (x[rH + 1][a + 3] != ' ' || x[rH + 1][aright + 3] != ' ')
		{
			ss = 0;
		}

	}
	//-------------------------------------------------
	if (sw == 0)
	{
		if (cth == 0)
		{
			x[rH][cH] = '0';
			x[rH + 1][cH] = '|';
			x[rH + 1][cH + 1] = '\\';
			x[rH + 1][cH - 1] = '//';
			x[rH + 2][cH + 1] = '\\';
			x[rH + 2][cH - 1] = '//';
		}
		if (cth == 1)
		{
			x[rH][cH] = ' ';
			x[rH + 1][cH] = ' ';
			x[rH + 1][cH + 1] = ' ';
			x[rH + 1][cH - 1] = ' ';
			x[rH + 2][cH + 1] = ' ';
			x[rH + 2][cH - 1] = ' ';
		}
	}
	if (sw == 1)
	{
		if (cth == 0)
		{
			x[rH + 2][cH] = 247;
			x[rH + 2][cH + 1] = 220;
			x[rH + 2][cH + 2] = 220;
			x[rH + 2][cH + 3] = '0';
		}
		if (cth == 1)
		{
			x[rH + 2][cH] = ' ';
			x[rH + 2][cH + 1] = ' ';
			x[rH + 2][cH + 2] = ' ';
			x[rH + 2][cH + 3] = ' ';



		}
	}
	//------Shoot going left-------------
	if (ss2 == 1)
	{
		if (cts2 == 0 || cts2 < 1)
		{
			x[rH + 1][a2 - 2] = 'o';

			cts2++;
		}
		if (cts2 == 1)
		{
			a2--;
			cts2 = 0;
		}
		if (x[rH + 1][a2 - 3] != ' ')
		{
			ss2 = 0;
			cts2 = 0;
		}

	}
	//----------------------------------------
}

void laser2(char x[][80], int& ct2)
{
	if (ct2 == 0 || ct2 < 40)
	{
		x[18][63] = '|';
		x[19][63] = '|';
		x[20][63] = '|';
		x[21][63] = '|';
		x[22][63] = '|';
		ct2++;
	}
	if (ct2 == 40 || ct2 < 70)
	{
		ct2++;
	}
	if (ct2 == 70)
	{
		ct2 = 0;
	}

}

void laser(char x[][80], int& ct)
{

	if (ct == 0 || ct < 30)
	{
		x[18][29] = '\\';
		x[19][30] = '\\';
		x[20][31] = '\\';
		x[21][32] = '\\';
		x[22][33] = '\\';

		x[18][27] = '/';
		x[19][26] = '/';
		x[20][25] = '/';
		x[21][24] = '/';
		x[22][23] = '/';
		ct++;
	}
	if (ct == 30 || ct < 50)
	{
		ct++;
	}
	if (ct == 50)
	{
		ct = 0;
	}
}

void Blaser(char x[][80], int& ct6)
{
	if (ct6 < 10)
	{
		x[4][14] = '.';
		x[4][13] = '.';
		x[4][12] = '.';
		x[4][11] = '.';
		x[4][10] = '.';
		x[4][9] = '.';
		x[4][8] = '.';
		x[4][7] = '.';
		x[4][6] = '.';
		ct6++;
	}
	if (ct6 == 10 || ct6 < 30)
	{
		ct6++;
	}
	if (ct6 == 30)
	{
		ct6 = 0;
	}
}


//void End(char x[][80], int& rH, int& cH, int& cte)
//{
	//if (x[rH][cH] == x[9][78] || x[rH + 1][cH] == x[9][78] || x[rH][cH + 1] == x[9][78] || x[rH][cH - 1] == x[9][78] || x[rH + 2][cH + 1] == x[9][78] || x[rH + 2][cH - 1] == x[9][78])
	//{
		//cte = 1;
	//}
//}

void laser4(char x[][80], int& ct2)
{
	x[3][71] = '||';
	x[3][73] = '||';
	x[3][72] = 210;

	if (ct2 == 0 || ct2 < 30)
	{
		x[4][72] = '|';
		x[5][72] = '|';
		x[6][72] = '|';
		x[7][72] = '|';
		x[8][72] = '|';
		x[9][72] = '|';
		ct2++;
	}
	if (ct2 == 40 || ct2 < 70)
	{
		ct2++;
	}
	if (ct2 == 70)
	{
		ct2 = 0;
	}
}

void laser3(char x[][80], int& ct2)
{
	x[3][64] = '||';
	x[3][62] = '||';
	x[3][63] = 210;

	if (ct2 == 0 || ct2 < 30)
	{
		x[4][63] = '|';
		x[5][63] = '|';
		x[6][63] = '|';
		x[7][63] = '|';
		x[8][63] = '|';
		x[9][63] = '|';
		ct2++;
	}
	if (ct2 == 40 || ct2 < 70)
	{
		ct2++;
	}
	if (ct2 == 70)
	{
		ct2 = 0;
	}

}

void SetEnmy(char x[][80], int rE, int cE, int& ctd)
{
	if (ctd == 0)
	{
		x[rE][cE] = '0';
		x[rE + 1][cE] = 178;
		x[rE + 1][cE - 1] = 196;
		x[rE + 1][cE - 2] = 196;
		x[rE + 1][cE + 1] = 196;
		x[rE + 1][cE + 2] = 196;
		x[rE + 2][cE - 1] = '//';
		x[rE + 2][cE + 1] = '\\';
	}

	if (ctd == 1)
	{
		x[rE][cE] = ' ';
		x[rE + 1][cE] = ' ';
		x[rE + 1][cE - 1] = ' ';
		x[rE + 1][cE - 2] = ' ';
		x[rE + 1][cE + 1] = ' ';
		x[rE + 1][cE + 2] = ' ';
		x[rE + 2][cE - 1] = ' ';
		x[rE + 2][cE + 1] = ' ';
	}



}

void SetEnmy1(char x[][80], int rE, int cE, int& ctd2)
{

	if (ctd2 == 0)
	{
		x[rE][cE] = '0';
		x[rE + 1][cE] = 178;
		x[rE + 1][cE - 1] = 196;
		x[rE + 1][cE - 2] = 196;
		x[rE + 1][cE + 1] = 196;
		x[rE + 1][cE + 2] = 196;
		x[rE + 2][cE - 1] = '//';
		x[rE + 2][cE + 1] = '\\';
	}
	if (ctd2 == 1)
	{
		x[rE][cE] = ' ';
		x[rE + 1][cE] = ' ';
		x[rE + 1][cE - 1] = ' ';
		x[rE + 1][cE - 2] = ' ';
		x[rE + 1][cE + 1] = ' ';
		x[rE + 1][cE + 2] = ' ';
		x[rE + 2][cE - 1] = ' ';
		x[rE + 2][cE + 1] = ' ';


	}
}
//void SetEnmy4(char x[][80], int rE, int cE, int& ctd1)
//{
	//x[rE][cE] = '0';
	//x[rE + 1][cE] = 178;
	//x[rE + 1][cE - 1] = 196;
	//x[rE + 1][cE - 2] = 196;
	//x[rE + 1][cE + 1] = 196;
	//x[rE + 1][cE + 2] = 196;
	//x[rE + 2][cE - 1] = '//';
	//x[rE + 2][cE + 1] = '\\';
//}

//void SetWeapon(char x[][80], int rW, int cW)
//{
//	x[rW][cW] = 217;
//	x[rW][cW - 1] = 192;
//	x[rW - 1][cW - 1] = 191;
//	x[rW - 1][cW - 2] = 196;
//	x[rW - 1][cW - 3] = 192;
//	x[rW - 2][cW - 3] = 218;
//	x[rW - 2][cW - 2] = 196;
//	x[rW - 2][cW - 1] = 196;
//	x[rW - 2][cW] = 191;
//	x[rW - 1][cW] = '||';
//}

void climbladder(char x[][80], int& rL, int& cL, int& rH, int& cH, char& O)
{
	if (O == 'c')
	{
		rH -= 7;
	}
}

void SetLadder(char x[][80], int rL, int cL)
{
	x[rL][cL] = 196;
	x[rL][cL + 1] = 196;
	x[rL][cL + 2] = 186;
	x[rL][cL - 1] = 186;
	x[rL + 1][cL] = 196;
	x[rL + 1][cL + 1] = 196;
	x[rL + 1][cL + 2] = 186;
	x[rL + 1][cL - 1] = 186;
	x[rL + 2][cL] = 196;
	x[rL + 2][cL + 1] = 196;
	x[rL + 2][cL + 2] = 186;
	x[rL + 2][cL - 1] = 186;
	x[rL + 3][cL] = 196;
	x[rL + 3][cL + 1] = 196;
	x[rL + 3][cL + 2] = 186;
	x[rL + 3][cL - 1] = 186;
	x[rL + 4][cL] = 196;
	x[rL + 4][cL + 1] = 196;
	x[rL + 4][cL + 2] = 186;
	x[rL + 4][cL - 1] = 186;
	x[rL + 5][cL] = 196;
	x[rL + 5][cL + 1] = 196;
	x[rL + 5][cL + 2] = 186;
	x[rL + 5][cL - 1] = 186;
	x[rL + 5][cL + 2] = 186;

}

void SetEnmy2(char x[][80], int rE, int cE, int& ctd3)
{
	if (ctd3 == 0)
	{
		x[rE][cE] = '0';
		x[rE + 1][cE] = 178;
		x[rE + 1][cE - 1] = 196;
		x[rE + 1][cE - 2] = 196;
		x[rE + 1][cE + 1] = 196;
		x[rE + 1][cE + 2] = 196;
		x[rE + 2][cE - 1] = '//';
		x[rE + 2][cE + 1] = '\\';
	}
	if (ctd3 == 1)
	{
		x[rE][cE] = ' ';
		x[rE + 1][cE] = ' ';
		x[rE + 1][cE - 1] = ' ';
		x[rE + 1][cE - 2] = ' ';
		x[rE + 1][cE + 1] = ' ';
		x[rE + 1][cE + 2] = ' ';
		x[rE + 2][cE - 1] = ' ';
		x[rE + 2][cE + 1] = ' ';
	}
}

void SetStone(char x[][80], int rS, int cS)
{
	x[rS + 1][cS] = 219;
	x[rS + 1][cS - 1] = 219;
	x[rS + 1][cS - 2] = 219;
	x[rS + 1][cS - 3] = 219;
}

void SetStone1(char x[][80], int rS, int cS)
{
	x[rS + 2][cS] = 219;                                            
	x[rS + 2][cS - 1] = 219;
	x[rS + 2][cS - 2] = 219;
	x[rS + 2][cS - 3] = 219;
}

void SetStone2(char x[][80], int rS, int cS)
{
	x[rS + 1][cS] = 219;
	x[rS + 1][cS - 1] = 219;
	x[rS + 1][cS - 2] = 219;
	x[rS + 1][cS - 3] = 219;
}

//void SetBridge(char x[][80], int rB, int cB)
//{
	//x[rB][cB] = 196;
	//x[rB][cB + 1] = 196;
	//x[rB][cB + 2] = 196;
	//x[rB][cB + 3] = 196;
	//x[rB][cB + 4] = 196;
	//x[rB][cB + 5] = 196;
//}

void fillelevatorinx(char x[][80], int& ra, int& ca, int& rH, int& cH)
{
	x[ra + 7][ca] = '-';
	x[ra + 7][ca + 1] = '-';
	x[ra + 7][ca + 2] = '-';
	x[ra + 7][ca + 3] = '-';
	x[ra + 8][ca - 1] = '|';
	x[ra + 9][ca - 1] = '|';
	x[ra + 11][ca - 1] = '|';
	x[ra + 10][ca - 1] = '|';
	x[ra + 12][ca] = '-';
	x[ra + 12][ca + 1] = '-';
	x[ra + 12][ca + 2] = '-';
	x[ra + 12][ca + 3] = '-';

	if (x[ra + 7][ca - 1] == ' ')
	{
		if (x[ra + 10][ca + 1] != ' ')
		{
			ra--;
			rH--;
		}
	}
}

void MoveEnmyPos(int& rE, int& cE)
{
	if (cE > 35)
	{
		cE--;
	}
	else
	{
		cE = 55;
	}
}

void MoveEnmyPos1(int& rE, int& cE)
{
	if (cE < 65)
	{
		cE++;
	}
	else
	{
		cE = 43;
	}
}

void MoveEnmyPos2(int& rE, int& cE)
{
	if (cE > 25)
	{
		cE--;
	}
	else
	{
		cE = 40;
	}
}

void MoveEnmyPos3(int& rE, int& cE)
{
	if (rE > 10)
	{
		rE--;
	}
	else
	{
		rE = 13;
	}
}

//void MoveWeapPos(int& rW, int& cW)
//{
	//if (cW > 32)
	//{
		//cW--;
	//}
	//else
	//{
		//cW = 52;
	//}
//}

void MoveBridge(int& rB, int& cB)
{
	if (rB > 4)
	{
		rB--;
	}
	else
	{
		rB = 9;
	}
}

void SetDoor(char x[][80], int rD, int cD)
{
	x[rD][cD] = 186;
	x[rD + 1][cD] = 186;
}

void MoveDoor(int& rD, int& cD)
{
	if (rD < 9 && rD > 3)
	{
		rD--;
	}
	else
	{
		rD = 8;
	}
}

void Ground(char x[][80], int& ct4)
{
	x[9][45] = 'U';
	x[9][44] = 186;
	x[9][46] = 186;
	if (ct4 < 40)
	{
		x[8][45] = 233;
		x[7][46] = 233;
		x[7][44] = 233;
		x[6][45] = 233;
		x[5][44] = 233;
		x[5][46] = 233;
		ct4++;
	}
	if (ct4 == 40 || ct4 <70)
	{
		ct4++;
	}
	if (ct4 == 70)
	{
		ct4 = 0;
	}
	
}

void cout_mat_to_screen(char x[][80])
{
	system("cls");
	for (int r = 0; r < 24; r++)
	{
		for (int c = 0; c < 80; c++)
		{
			cout << x[r][c];
		}
	}

}

void SetOurMat2(char y[][80])
{
	for (int r = 0; r < 24; r++)
	{
		for (int c = 0; c < 80; c++)
		{
			y[r][c] = ' ';
		}
	}

	y[2][0] = 201;
	y[23][0] = 200;
	y[2][79] = 187;
	y[23][79] = 188;

	for (int r = 3; r < 23; r++)
	{
		y[r][0] = 186;
	}

	for (int r = 3; r < 23; r++)
	{
		y[r][79] = 186;
	}

	for (int c = 1; c < 79; c++)
	{
		y[2][c] = 205;
	}

	for (int c = 1; c < 79; c++)
	{
		y[23][c] = 205;
	}
}

void cout_mat_to_screen2(char y[][80])
{
	system("cls");
	for (int r = 0; r < 24; r++)
	{
		for (int c = 0; c < 80; c++)
		{
			cout << y[r][c];
		}
	}

}

void main()
{
	char x[24][80];
	char y[24][80];
	int rH = 20;
	int cH = 3;
	int rh = 20;
	int ch = 5;
	int rL = 17;
	int cL = 75;
	int rE = 20;
	int cE = 55;
	int rW = 21;
	int cW = 52;
	int rS = 14;
	int cS = 30;
	int rs1 = 12;
	int cs1 = 25;
	int rs2 = 14;
	int cs2 = 20;
	int re1 = 13;
	int ce1 = 50;
	int rB = 9;
	int cB = 38;
	int ra = 4;
	int ca = 4;
	int re = 20;
	int ce = 31;
	int ct = 0;
	int ct2 = 0;
	int ct3 = 0;
	int ct4 = 0;
	int ct6 = 0;
	int sw = 0;
	int cts = 0;
	int re2 = 7;
	int ce2 = 40;
	int ctj = 0;
	int ss = 0;
	int a;
	int ju = 0;
	int ctju = 0;
	int ss2 = 0;
	int cte = 0;
	int a2 = 0;
	int cts2 = 0;
	int mulleft = 0;
	int mulright = 0;
	int aleft = 0;
	int aright = 0;
	int ex = 0;
	int re3 = 13;
	int ce3 = 40;
	int ctd = 0;
	int ctd1 = 0;
	int cth = 0;
	int rD = 8;
	int cD = 20;
	int he = 40;
	int ctd2 = 0;
	int cthede = 0;
	int ctd3 = 0;
	char enter;
	char ent;

	cout << "welcome to shooting game" << endl;
	cout << endl;
	cout << endl;
	cout << endl;
	cout << endl;
	cout << "use ( a and d for movement) and (w) to shoot laser on enemies " << endl;
	cout << endl;
	cout << endl;
	cout << endl;
	cout << endl;
	cout << endl;
	cout << "                    to start a new game press z botton" << endl;
	cin >> enter;

	if (enter == 'z')
	{
		for (;;)
		{
			for (; !_kbhit(); )
			{

				SetOurMat(x, cte);

				SetHero(x, rH, cH, sw, cts, ss, a, ss2, a2, cts2, mulright, mulleft, aright, aleft, cth);
				SetEnmy(x, rE, cE, ctd);
				SetEnmy1(x, re1, ce1, ctd1);
				SetEnmy2(x, re2, ce2, ctd);
				//SetEnmy4(x, re3, ce3, ctd);
				//SetWeapon(x, rW, cW);
				SetLadder(x, rL, cL);
				SetStone(x, rS, cS);
				SetStone1(x, rs1, cs1);
				SetStone2(x, rs2, cs2);
				Ground(x, ct4);
				//SetBridge(x, rB, cB);
				SetDoor(x, rD, cD);
				fillelevatorinx(x, ra, ca, rH, cH);
				MoveEnmyPos(rE, cE);
				MoveEnmyPos1(re1, ce1);
				MoveEnmyPos2(re2, ce2);
				MoveEnmyPos3(re3, ce3);
				//MoveWeapPos(rW, cW);
				MoveDoor(rD, cD);
				MoveBridge(rB, cB);
				laser(x, ct);
				laser2(x, ct2);
				laser3(x, ct2);
				laser4(x, ct2);
				Blaser(x, ct6);
				death(x, rH, cH, rE, cE, ctd, cth);
				cout_mat_to_screen(x);
				if (cth == 1)
				{
					cout << "game over" << endl;
					cout << "nice try MAN .........................................................." << endl;
					break;
				}
				if (x[9][77] != ' ')
				{
					cout << "congratulations you won !!" << endl;
					cout << "Good job !" << endl;
					cout << "enter n to enter the new level" << endl;
					cin >> ent;
					if (ent == 'v')
					{
						for (; ;)
						{
							for (; !_kbhit;)
							{
								SetOurMat2(y);
								cout_mat_to_screen2(y);
							}
						}
					}
				}
			}
			char Q;
			Q = _getch();
			MoveHeroPosition(x, rH, cH, Q, sw, cts, ctj, ss, a, ss2, a2, mulright, mulleft, aright, aleft, ex);
			char O;
			O = _getch();
			climbladder(x, rL, cL, rH, cH, O);
		}
	}
	system("pause");
}