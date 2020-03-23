// Created on Mon March 23 2020
int l_motor = 0; 
int r_motor = 3;
int forward = 40;
int backward = -35;
int left = 50;
int right = -50;
int turn_pause = 450;
int turn_pause_dos = 850;
int pause = 1500;
int straight = 12500;

void forwards(){ //go forward
    motor(l_motor,forward);
    motor(r_motor,forward);
}
void turn(){ //turn
	motor(l_motor,left);
    motor(r_motor,right);
	msleep(turn_pause);
	ao();
}
void turn_dos(){ //turn
	motor(l_motor,right);
    motor(r_motor,left);
	msleep(turn_pause_dos);
	ao();
}


int main()
{
	forwards();
	msleep(pause);
	turn();
	forwards();
	msleep(straight);
	turn_dos();
    return 0;
}
