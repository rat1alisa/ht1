# ht1



#include <iostream>
#include <algorithm>
#include <iomanip>
using namespace std;

template <typename T>
class ARR 
{
private:
    T** arr = new T * [5];
    T** arrr = new T * [5];
    T** dop = new T * [5]; 
public:
    //-----operator
    friend ARR operator +(ARR& a2, ARR& b2)
    {
        return ARR { a2.a + b2.b};
    }
    friend ARR operator -(ARR& a2, ARR& b2)
    {
        return ARR { a2.a - b2.b};
    }
    friend ARR operator *(ARR& a2, ARR& b2)
    {
        return ARR { a2.a * b2.b};
    }
    friend ARR operator /(ARR& a2, ARR& b2)
    {
        return ARR { a2.a / b2.b};
    }
    //-----
    
    void RArr() //randarr
    {
        srand(time(NULL));
        int max = 0;
        int min = 0;
        int max2 = 0;
        int min2 = 0;
        cout << "   First Array: \n";
        for (int i = 0; i < 5; i++) 
        {
            arr[i] = new T[i];
        }
        for (int i = 0; i < 5; i++) 
        {
            for (int j = 0; j < 5; j++)
            {
                arr[i][j] = rand()%5;
                //cout.width(3);
                cout << arr[i][j] << " ";
                if (max > arr[i][j])
                {
                    max = arr[i][j];
                }
                if (min < arr[i][j])
                {
                    min = arr[i][j];
                }
            }
            cout << endl;
        }
        cout << "\nMax - " << max << endl;
        cout << "Min -  " << min;
        cout << endl;
        //
        cout << "   Second Array: \n";
        for (int i = 0; i < 5; i++)
        {
            arrr[i] = new T[i];
        }
        for (int i = 0; i < 5; i++)
        {
            for (int j = 0; j < 5; j++)
            {
                arrr[i][j] = rand()%15;
                //cout.width(3);
                cout << arrr[i][j] << " ";
                if (max2 > arrr[i][j])
                {
                    max2 = arrr[i][j];
                }
                if (min2 < arrr[i][j])
                {
                    min2 = arrr[i][j];
                }
            }
            cout << endl;
        }
        cout << "\nMax - " << max2 << endl;
        cout << "Min -  " << min2 ;
        cout << endl;
    }
    //----------arithmetic operations
    void Addition()
    {
        cout << "\tAddition: \n";
        for (int i = 0; i < 5; i++)
        {
            dop[i] = new T[i];
        }
        for (int i = 0; i < 5; i++) 
        {
            for (int j = 0; j < 5; j++)
            {
                dop[i][j] = arr[i][j] + arrr[i][j];
                cout << dop[i][j] << " ";
            }
            cout << endl;
        }
    }
    void Substraction()
    {
        cout << "\tSubstraction: \n";
        for (int i = 0; i < 5; i++)
        {
            dop[i] = new T[i];
        }
        for (int i = 0; i < 5; i++)
        {
            for (int j = 0; j < 5; j++)
            {
                dop[i][j] = arr[i][j] - arrr[i][j];
                cout << dop[i][j];
            }
            cout << endl;
        }
    }
    void Multiplication()
    {
        cout << "\tMultiplication: \n";
        for (int i = 0; i < 5; i++)
        {
            dop[i] = new T[i];
        }
        for (int i = 0; i < 5; i++)
        {
            for (int j = 0; j < 5; j++)
            {
                dop[i][j] = arr[i][j] * arrr[i][j];
                cout << dop[i][j];
            }
            cout << endl;
        }
    }
    void Division() 
    {
        cout << "\tDivision: \n";
        for (int i = 0; i < 5; i++)
        {
            dop[i] = new T[i];
        }
        for (int i = 0; i < 5; i++)
        {
            for (int j = 0; j < 5; j++)
            {
                dop[i][j] = arr[i][j] / arrr[i][j];
                cout << dop[i][j];
            }
            cout << endl;
        }
    }
    //-----delete
    void Delete() //deleterand
    {
        for (int i = 0; i < 5; i++)
        {
            delete[] arr[i];
        }
        delete[] arr;
        for (int i = 0; i < 5; i++)
        {
            delete[] arrr[i];
        }
        delete[] arrr;
        for (int i = 0; i < 5; i++)
        {
            delete[] dop[i];
        }
        delete[] dop;
    }
};

template <typename T>
class MATRIX 
{
private:
    T** ar = new T * [5];
    T** ar2 = new T * [5];
    T** dop2 = new T * [5]; 
public:
    //-----operator
    friend MATRIX operator +(MATRIX& a2, MATRIX& b2)
    {
        return MATRIX { a2.a + b2.b};
    }
    friend MATRIX operator -(MATRIX& a2, MATRIX& b2)
    {
        return MATRIX { a2.a - b2.b};
    }
    friend MATRIX operator *(MATRIX& a2, MATRIX& b2)
    {
        return MATRIX { a2.a * b2.b};
    }
    friend MATRIX operator /(MATRIX& a2, MATRIX& b2)
    {
        return MATRIX { a2.a / b2.b};
    }
    //-----
    
    void PrMa()
    {
        cout << "\tEnter first arr: " << endl;
        for (int i = 0; i < 3; i++)
        {
            ar[i] = new T[i];
        }
        for (int i = 0; i < 3; i++)
        {
            for (int j = 0; j < 3; j++)
            {
                cin >> ar[i][j];
                cout << ar[i][j];
            }
            cout << endl;
        }
        cout << endl;
        cout << "\tEnter second arr: " << endl << "->";
        for (int i = 0; i < 3; i++)
        {
            ar2[i] = new T[i];
        }
        for (int i = 0; i < 3; i++)
        {
            for (int j = 0; j < 3; j++)
            {
                cin >> ar2[i][j];
                cout << ar2[i][j];
            }
            cout << endl;
        }
        cout << endl;
    }
    //----------arithmetic operations
    void Addition1()
    {
        cout << "\tAddition: \n";
        for (int i = 0; i < 5; i++)
        {
            dop2[i] = new T[i];
        }
        for (int i = 0; i < 5; i++) 
        {
            for (int j = 0; j < 5; j++)
            {
                dop2[i][j] = ar[i][j] + ar2[i][j];
                cout << dop2[i][j] << " ";
            }
            cout << endl;
        }
    }
    void Substraction1()
    {
        cout << "\tSubstraction: \n";
        for (int i = 0; i < 5; i++)
        {
            dop2[i] = new T[i];
        }
        for (int i = 0; i < 5; i++)
        {
            for (int j = 0; j < 5; j++)
            {
                dop2[i][j] = ar[i][j] - ar2[i][j];
                cout << dop2[i][j];
            }
            cout << endl;
        }
    }
    void Multiplication1()
    {
        cout << "\tMultiplication: \n";
        for (int i = 0; i < 5; i++)
        {
            dop2[i] = new T[i];
        }
        for (int i = 0; i < 5; i++)
        {
            for (int j = 0; j < 5; j++)
            {
                dop2[i][j] = ar[i][j] * ar2[i][j];
                cout << dop2[i][j];
            }
            cout << endl;
        }
    }
    void Division1() 
    {
        cout << "\tDivision: \n";
        for (int i = 0; i < 5; i++)
        {
            dop2[i] = new T[i];
        }
        for (int i = 0; i < 5; i++)
        {
            for (int j = 0; j < 5; j++)
            {
                dop2[i][j] = ar[i][j] / ar2[i][j];
                cout << dop2[i][j];
            }
            cout << endl;
        }
    }
    //-----delete
    void DeleteRand()
    {
        for (int i = 0; i < 5; i++)
        {
            delete[] ar[i];
        }
        delete[] ar;
        for (int i = 0; i < 5; i++)
        {
            delete[] ar2[i];
        }
        delete[] ar2;
        for (int i = 0; i < 5; i++)
        {
            delete[] dop2[i];
        }
        delete[] dop2;
    }
};

int main()
{
    ARR <int> a;
    MATRIX <int> b;
    int c;
    int c1;
    int c2;
    cout << "\tMake your choice: " << endl;
    cout << "1. Fill out automatically." << endl;
    cout << "2. Fill in the matrix yourself." << endl;
    do {
        cin >> c1;
        switch (c1)
        {
        case 1: (c1 == 1); 
        {
            a.RArr();
            cout << "\n1. Addition" << endl;
            cout << "2. Substraction" << endl;
            cout << "3. Multiplication" << endl;
            cout << "4. Division" << endl;
            cout << "5. Other" << endl;
            do {
                cin >> c;
                switch (c) 
                {
                case 1: (c == 1);
                {
                    a.Addition();
                    break;
                }
                case 2: (c == 2);
                {
                    a.Substraction();
                    break;
                }
                case 3: (c == 3);
                {
                    a.Multiplication();
                    break;
                }
                case 4: (c == 4); 
                {
                    a.Division();
                    break;
                }
                case 5: (c == 5);
                {
                    a.Delete();
                    cout << "\nThe matrix has been removed.";
                    break;
                }
                default:
                {
                    cout << "ERROR";
                    break;
                }
                }
            } while (c != 5);
            break;
        }
        case 2: (c1 == 2);
        {
            b.PrMa();
            cout << "\n1. Addition" << endl;
            cout << "2. Substraction" << endl;
            cout << "3. Multiplication" << endl;
            cout << "4. Division" << endl;
            cout << "5. Other" << endl;
            do {
                cin >> c2;
                switch (c2)
                {
                case 1: (c2 == 1);
                {
                    b.Addition1();
                    break;
                }
                case 2: (c2 == 2);
                {
                    b.Substraction1();
                    break;
                }
                case 3: (c2 == 3);
                {
                    b.Multiplication1();
                    break;
                }
                case 4: (c2 == 4);
                {
                    b.Division1();
                    break;
                }
                case 5: (c2 == 5);
                {
                    break;
                }
                default:
                {
                    cout << "ERROR";
                    break;
                }
                }
            } while (c2 != 5);
            break;
        }
        case 3: (c1 == 3);
        {
            break;
        }
        default:
        {
            cout << "ERROR";
            break;
        }
        }
    } while (c1 != 3);
    return 0;
};
