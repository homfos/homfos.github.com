
#include <iostream>
 
class Base{
    public:
        virtual void Print(){ std::cout << "print base" << std::endl; }
};

class Drivate : public Base{
    public:
        virtual void Print() { std::cout << "print Drivate" << std::endl; }
        int a;
};

int main(void)
{
    Drivate d;
    Base b;
    b.Print();
    b = d;
    b.Print();
    Base &c = d;
    c.Print();
}

执行结果：
print base
print base
print Drivate