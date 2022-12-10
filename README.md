# c22include<iostream.h>

#include<conio.h>

class student

{

protected:

    int roll_number;

    string name;

public:

    void get_number(int a, string s)

    {

        roll_number = a;

        name = s;

    }

    void put_number(void)

    {

        cout << "Roll No:" << roll_number << "\n";

          cout << "Name :" << name << "\n";

    }

};

class test : public student

{

protected:

    float cpp, java,python;

public:

    void get_marks(float x, float y,float  z)

    {

        cpp = x;

        java = y;

        python = z;

    }

    void put_marks(void)

    {

        cout << "Marks obtained"

             << "\n"

             << "C++ = " << cpp << "\n"

             << "JAVA = " << java << "\n" 

             << "PYTHON = " << python << "\n";

    }

};

class sports

{

protected:

    float score;

public:

    void get_score(float s)

    {

        score = s;

    }

    void put_score(void)

    {

        cout << "Sports : " << score << "\n";

    }

};

class result : public test, public sports

{

    float total;

public:

    void display(void);

};

void result ::display(void)

{

    total = cpp + java + python +score;

    put_number();

    put_marks();

    put_score();

    cout << "Total Score:" << total << "\n";

}

int main()

{

    result student[100];

    int n,roll;

    string name;

    float cpp,java,python,sport;

    cout<<"Enter the number of students "<<endl;

    cin>>n;

    for(int i=0;i<n;i++)

    {

        cout<<"Enter the roll no and name of the student "<<endl;

        cin>>roll>>name;

        cout<<"Enter the marks of cpp , java , puython and sports "<<endl;

        cin>>cpp>>java>>python>>sport;

        student[i].get_number(roll,name);

        student[i].get_marks(cpp,java,python);

        student[i].get_score(sport);

        

    }

    for(int i=0;i<n;i++)

    {   

       

        cout<<"Details of Student "<<i+1<<endl;

         cout<<"===================================="<<endl;

        student[i].display();

       cout<<"===================================="<<endl;

        

    }

    return 0;

}
