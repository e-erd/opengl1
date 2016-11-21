# opengl1
#include <gl/freeglut.h>

void init();
void display(void);
void drawObject();

//wymiary okna
int w_width = 640;
int w_height = 480;

int main(int argc, char **argv)
{
	// inicjalizacja biblioteki GLUT
	glutInit(&argc, argv);
	glutInitWindowSize(w_width, w_height);
	//wybor opcji wyswietlania okna 
	//parametr GLUT_RGBA - definicja kolorów w modelu RGBA
	//parametr GLUT_DOUBLE - podwojne buforowanie
	glutInitDisplayMode(GLUT_RGBA | GLUT_DOUBLE);
	glutCreateWindow("Okno w OpenGL FreeGlut");
	init();
	//Funkcja wykonująca wywołanie zwrotne
	glutDisplayFunc(display);
	//Uruchomienie pętli przetwarzania zdarzen GLUT
	glutMainLoop();

	return 0;
}

//Inicjalizacja maszyny stanu OpenGL
void init()
{
	//kolor tła - zawartość bufora koloru
	glClearColor(0.0, 0.0, 0.0, 0.0);
}
//Definicja funkcji przekazywanej do glutDisplayFunc
void display(void)
{
	//Czyszczenie bufora ramki do koloru okreslonego w funkcji maszyny stanu
	glClear(GL_COLOR_BUFFER_BIT);
	drawObject();
	//Kopiowanie z bufora na ekran
	glutSwapBuffers();
}

//Funcja rysowania obiektu
void drawObject()
{

}
