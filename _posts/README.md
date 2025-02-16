//ReferenceMember.cpp
#include<iostream>;
using namespace std;

class AAA {
public:
	AAA()
	{
		cout << "empty object" << endl;
	}
	void ShowYourName()
	{
		cout << "I'm class AAA" << endl;
	}
};

class BBB {
private:
	AAA& ref;
	const int& num;
public:
	BBB(AAA& r, const int& n)
		:ref(r), num(n)  //이니셜라이저를 이용한 초기화
	{

	}
	void ShowYourName() {
		ref.ShowYourName();
		cout << "and" << endl;
		cout << "I'm class BBB" << endl;
	}
};

int main(void) {
	AAA obj1; // AAA obj1; 는 AAA()함수의 호출과 같다. 따라서 출력에 I'm class AAA 가 출력된다.
	BBB obj2(obj1, 20);
	obj2.ShowYourName();
	return 0;
}
//202-02-16