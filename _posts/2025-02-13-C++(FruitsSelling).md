#include <iostream>
#include <cstring>
using namespace std;

class FruitSeller {
private:
	int ApplePrice;
	int AppleNum;
	int myMoney;
public:
	void InitMembers(int price, int num, int money) {
		ApplePrice = price;
		AppleNum = num;
		myMoney = money;
		return;
	}
	int SaleApples(int money) {
		int num = money / ApplePrice;
		AppleNum -= num;
		myMoney += money;
		return num;
	}
	void ShowSalesResult(void) {
		cout << "남은 사과: " << AppleNum << endl;
		cout << "판매 수익: " << myMoney << endl;
		return;
	}
};

class FruitBuyer {
private:
	int myMoney;
	int AppleNum=0;
public:
	void InitMembers(int money) {
		myMoney = money;
	}
	void BuyApples(FruitSeller &seller,int money) {
		AppleNum += seller.SaleApples(money);
		myMoney -= money;
	}
	void ShowBuyResult(void) {
		cout << "현재 잔액: " << myMoney << endl;
		cout << "사과 개수: " << AppleNum << endl;
	}
};

int main(void) {
	FruitSeller seller;
	FruitBuyer buyer;
	seller.InitMembers(1000, 20, 0);
	buyer.InitMembers(5000);
	buyer.BuyApples(seller, 2000);

	cout << "과일 판매자의 현황" << endl;
	seller.ShowSalesResult();
	cout << endl;
	cout << "과일 구매자의 현황" << endl;
	buyer.ShowBuyResult();
	return 0;
}