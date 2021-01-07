# U5E2QuickSort
package QUICKSORT;

import java.util.ArrayList;
import java.util.List;

public class QUICKSORT{

    public static void main(String[] args) {
       List<Integer> lista = new ArrayList<Integer>();
       lista.add(10);
       lista.add(3);
       lista.add(7);
       lista.add(9);
       lista.add(8);
       lista.add(1);
      System.out.println("lista desordenada");
      for(int i=0;i<lista.size();i++){
          System.out.print(lista.get(i)+" ");
      }
        int izq=0, der=lista.size()-1;
        quicksort(lista, izq,der);
        System.out.println("\nLista ordenada: "+ "");
        for(int i=0;i<lista.size();i++){
          System.out.print(lista.get(i)+" ");
      }
      
    }

    private static void quicksort( List<Integer> lista , int izq, int der) {
    int pivote=lista.get(izq),aux, i=izq, d=der;        
 
     while(i < d){                                                             
     while(lista.get(i)<= pivote && i < d)
        i++; 
     while(lista.get(d) > pivote) 
        d--;           
       if (i < d){                                             
         aux=lista.get(i);                      
         lista.set(i,lista.get(d));
         lista.set(d,aux);
     }
   }
   
   lista.set(izq, lista.get(d));                                     
   lista.set(d,pivote);      
   
   if(izq < d-1)
      quicksort(lista,izq,d-1);         
   if(d+1 < der)
      quicksort(lista,d+1,der);         
   
}
}
