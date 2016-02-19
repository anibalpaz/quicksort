/*main.java*/
package quicksort;


public class main {
    
    public static void main(String[] args)
    {
        int array[] ={54,26,93,17,77,31,44,55,20};
        ordenador o = new ordenador();
        o.quicksort(array);
    }
/*ordenador.java*/

package quicksort;


public class ordenador {
    
    public int[] quicksort(int numeros[])
    {
        return quicksort(numeros,0,numeros.length-1);
    }
    public int[] quicksort(int numeros[],int izq,int der)
    {
        if(izq>=der)
            return numeros;
        int i=izq,d=der;
        if(izq!=der)
        {
            int pivote;
            int aux;
            pivote = izq;
            while(izq!=der)
            {
            
            while(numeros[der]>=numeros[pivote] && izq<der)
                der--;
            while(numeros[izq]<numeros[pivote] && izq<der)
                izq++;
            
            if(der!=izq)
            {
                aux = numeros[der];
                numeros[der]= numeros[izq];
                numeros[izq]= aux;}
            
            }
            if(izq==der){
                quicksort(numeros,i,izq-1);
                quicksort(numeros,izq,+1,d);
            }
        }
        else
            return numeros;
        return numeros;
    }
}

