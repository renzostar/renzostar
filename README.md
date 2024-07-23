/*Una dulceria vende chocolates a los precios dados en la siguiente tabla:

    TIPO DE CHOCOLATE    -     PRECIO UNITARIO
    
    primor               -     8.5
    dulzura              -     10
    tentacion            -     7
    explosion            -     12.5

La dulceria ofrece ofertas, segun como sigue:

    CANTIDAD DE CHOCOLATES    -     TASA DE DESCUENTO
    
    <5               -     4%
    >=5 y <10        -     6.5%
    >=10 y <15       -     9%
    >=15             -     11.5%

Adicionalmente, si el importe a pagar es NO MENOR de 250 soles, la tienda 
obsequia 3 caramelos por cada chocolate; caso contrario obsequia 2 caramelos por
cada chocolate.

Dado el tipo de chocolate y la cantidad comprada, mostrar el importe de la
compra, descuento total, importe a pagar y cantidad de caramelos obsequiados. */

#include <iostream>
using namespace std;

int main()
{
    // declaracion de variables
    int tipo, cantidad, caramelo;
    double precioUnitario, tasaD, descuentoTotal, importeCompra, importePago;
    
    // lectura de variables
    cout << "[1]PRIMOR\n";
    cout << "[2]DULZURA\n";
    cout << "[3]TENTACION\n";
    cout << "[4]EXPLOSION\n";
    cout << "----------------------------\n";
    cout << "Ingrese el tipo de chocolate: ";
    cin >> tipo;
    
    cout << "\nIngrese la cantidad de chocolates: ";
    cin >> cantidad;
    
    // asignacion precio unitario
    if(tipo == 1)
      precioUnitario = 8.5;
    else
        if(tipo == 2)
        precioUnitario = 10;
        else
            if(tipo == 3)
            precioUnitario = 7;
            else
                precioUnitario = 12.5;
    
    // calculo del importe de compra
    importeCompra = precioUnitario * cantidad;
    
    // asignacion tasa de descuento
    if(cantidad < 5)
      tasaD = 0.04;
    else
        if(cantidad >= 5 && cantidad < 10)
        tasaD = 0.065;
        else
            if(cantidad >= 10 && cantidad < 15)
            tasaD = 0.09;
            else
                tasaD = 0.115;
    
    // calculo del descuento total
    descuentoTotal = importeCompra * tasaD;
    
    //calculo del importe a pagar
    importePago = importeCompra - descuentoTotal;
    
    // asignacion de caramelos
    if(importePago >= 250)
      caramelo = 3 * cantidad;
    else
        caramelo = 2 * cantidad;
    
    cout << "\nEl importe de compra es: " << importeCompra;
    cout << "\nEl descuento total es: " << descuentoTotal;
    cout << "\nEl importe de pago es: " << importePago;
    cout << "\nLa cantidad de caramelos obsequiados es: " << caramelo;
}
