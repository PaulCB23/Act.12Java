# Act.12Java

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;

public class Act12Java {
    public static void main (String[] args) throws IOException{
        Scanner sc = new Scanner(System.in);
        BufferedReader lector = new BufferedReader(new InputStreamReader(System.in));

        String salir ;
        int opc;
        HashMap<String,Integer> agenda= new HashMap();
        String nombre;
        int numero;
        do{

            System.out.println("Agenda: elige una de las opciones: ");
            System.out.println("1) Mostrar lista");
            System.out.println("2) Agregar contacto");
            System.out.println("3) Eliminar contacto");
            opc=sc.nextInt();
            switch(opc){
                case 1:
                    for(Map.Entry<String, Integer> entry: agenda.entrySet()){
                        System.out.println("Nombre: "+entry.getKey()+"     Numero: "+entry.getValue());
                    }
                    break;

                case 2:
                    System.out.println("Ingrece el nombre del contacto ");
                    nombre=lector.readLine();
                    System.out.println("Ingrese el numero del contacto:");
                    numero=sc.nextInt();
                    if(!agenda.containsKey(nombre)){
                        agenda.put(nombre, numero);
                        System.out.println("Contacto agregado");
                    }else{
                        System.out.println("Contacto ya existe");
                    }

                    break;

                case 3:
                    System.out.println("Ingrese el nombre del contacto que quiere eliminar");
                    nombre=lector.readLine();
                    if(agenda.containsKey(nombre)){
                        agenda.remove(nombre);
                        System.out.println("Contacto eliminado");
                    }else{
                        System.out.println("El contacto no existe");
                    }
                    break;

            }
            System.out.println("Repetir menu?\n si o no");
            salir=lector.readLine();
        }while(salir.equals("si"));
    }
}
