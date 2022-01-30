// assignment-6
//bus
void a::add_new_number_of_bus()
{
cout&lt;&lt;"Enter Bus Number: ";
cin&gt;&gt;bus[t].bus_number;
cout&lt;&lt;"\nEnter Driver's Name: ";
cin&gt;&gt;bus[t].bus_driver;
cout&lt;&lt;"\nArrival Time: ";
cin&gt;&gt;bus[t].bus_arrival;
cout&lt;&lt;"\nDeparture: ";
cin&gt;&gt;bus[t].bus_depart;
cout&lt;&lt;"\nFrom: \t\t\t";
cin&gt;&gt;bus[t].b_from;
cout&lt;&lt;"\nTo: \t\t\t";
cin&gt;&gt;bus[t].b_to;
bus[t].empty();
cout&lt;&lt;"\New Bus Added Successfully \t\t\t";
t++;
}
void a::reservation()
{
int bus_seat;
char no[5];
top:
cout&lt;&lt;"Bus Number: ";
cin&gt;&gt;no;
int y;
for(y=0;y&lt;=t;y++)
{
if(strcmp(bus[y].bus_number, no)==0) break;
}
while(y&lt;=t)
{
cout&lt;&lt;"\nSeat Number: "; cin&gt;&gt;bus_seat; if(bus_seat&gt;32) { cout&lt;&lt;"\nThere are only 32 Seats Available in this Bus."; } else { if (strcmp(bus[y].bus_seat[bus_seat/4][(bus_seat%4)-1], "Empty")==0) { cout&lt;&lt;"Enter Passenger's Name: "; cin&gt;&gt;bus[y].bus_seat[bus_seat/4][(bus_seat%4)-1]; break; } else cout&lt;&lt;"The Seat Number. is Already Reserved.\n"; } } if(y&gt;t) { cout&lt;&lt;"Enter Correct Bus Number.\n"; goto top; }
}
void a::view()
{
int m;
char number[5];
cout&lt;&lt;"Enter Bus Number: ";
cin&gt;&gt;number;
for(m=0;m&lt;=t;m++)
{
if(strcmp(bus[m].bus_number, number)==0) break;
}
while(m&lt;=t)
{
bus_line('*');
cout&lt;&lt;"Bus Number: \t"&lt;&lt;bus[m].bus_number
&lt;&lt;"\nDriver: \t"&lt;&lt;bus[m].bus_driver&lt;&lt;"\t\tArrival Time: \t"
&lt;&lt;bus[m].bus_arrival&lt;&lt;"\tDeparture Time:"&lt;&lt;bus[m].bus_depart
&lt;&lt;"\nFrom: \t\t"&lt;&lt;bus[m].b_from&lt;&lt;"\t\tTo: \t\t"&lt;&lt;
bus[m].b_to&lt;&lt;"\n";
bus_line('*');
bus[0].position(m);
int d=1;
for (int x=0; x&lt;8; x++)
{
for(int y=0;y&lt;4;y++) { d++; if(strcmp(bus[m].bus_seat[x][y],"Empty")!=0) cout&lt;&lt;"\nThe Seat no "&lt;&lt;(d-1)&lt;&lt;" is Reserved for "&lt;&lt;bus[m].bus_seat[x][y]&lt;&lt;"."; }
}
break;
}
if(m&gt;t)
cout&lt;&lt;"Enter Correct Bus Number: ";
}
void a::position(int l)
{
int r=0;t=0;
for (int x =0; x&lt;8;x++)
{
cout&lt;&lt;"\n"; for (int z = 0;z&lt;4; z++) { r++; if(strcmp(bus[l].bus_seat[x][z], "Empty")==0) { cout.width(5); cout.fill(' '); cout&lt;&lt;r&lt;&lt;"."; cout.width(10); cout.fill(' '); cout&lt;&lt;bus[l].bus_seat[x][z]; t++; } else { cout.width(5); cout.fill(' '); cout&lt;&lt;r&lt;&lt;"."; cout.width(10); cout.fill(' '); cout&lt;&lt;bus[l].bus_seat[x][z]; } } }
cout&lt;&lt;"\n\nThere are "&lt;&lt;t&lt;&lt;" Seats Empty in Bus Number: "&lt;&lt;bus[l].bus_number;
}

