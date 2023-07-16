# Tienda
import java.util.Scanner;
public class Tienda{
   public static void main(String args[]){
   Scanner leer = new Scanner(System.in);
   
   //Fijamos datos necesarios
   int opc = 0;
   float PrecioL = 43.90f, PrecioT = 0, Descuento = 0,contL = 0;
   float contPT = 0, contD = 0, Litros = 0, Almacen = 2301;
   
   do{
   System.out.println("Bienvenido a licoleria MEVA");
   System.out.println("Realizar una compra [1]");
   System.out.println("Finalizar el programa[2]");
   opc = leer.nextInt();
   
      switch(opc){
         case 1:
         System.out.println("Ingrese la cantidad de alcohol a comprar");
         System.out.printf("La cantidad de alcohol en el almacen es de: %.2f Litros\n ", Almacen);
         Litros = leer.nextFloat();
         
         if(Litros > Almacen){
            System.out.print("La cantidad de alcohol es insuficiente\n");
            System.out.print("Precione ENTER para continuar\n");
            leer.nextLine(); leer.nextLine();
            break;
         }
         
         //Almaenamos los datos de litros vendidos
         //y se los quitamos al almacen
         contL += Litros;
         Almacen -= Litros;
         
         //se realiza un descuento si es que se cumple la condicion
         if(Litros > 7){
            PrecioT = Litros * PrecioL;
            Descuento = PrecioT * 0.08f;
            PrecioT -= Descuento;
            contPT += PrecioT;
            contD += Descuento;
             
         }
         
         
         System.out.printf("\nLitros que compro:\n "+ Litros);
         System.out.printf("\nPago antes del descuento:\n "+ Litros * PrecioL);
         System.out.printf("\nPago despues del descuento:\n "+ PrecioT);
         System.out.printf("\nDescuento realizado: \n "+ Descuento);
         System.out.println("\n******************************************************");
         
         
         break;   
         
         case 2:
         System.out.println("Programa finalizado");
                    break;
                    
                default:
                    System.out.println("Opcion no valida");
                    System.out.println("Precione ENTER para continuar");
                    leer.nextLine(); leer.nextLine();
      }
   }while(opc != 2);
   System.out.println("Cantidad de litros de alcohol vendidos: " + contL);
   System.out.println("Dinero otenido por las ventas: " + contPT);
   System.out.println("Dinero perdido por los descuentos: " + contD );
   System.out.println("Litros restantes de alcohol: " + (Almacen));
   System.out.println("[MEVA]");
   }
}
