# Mail2
Main.java
import java.util.ArrayList;
import java.util.Scanner;

public class Main {
	static final int NPERSONAS = 5;
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		ArrayList <Persona> personas = new ArrayList<>();
		for (int i = 1; i<=NPERSONAS; i++){
			System.out.print("Nombre " + i + ": ");
			System.out.flush();
			String nombre = sc.nextLine();
			Persona p = new Persona(nombre,email);
			personas.add(p);
		}
	for (Persona p: personas){
		p.imprimir();
	}
	System.out.print("introduce persona para ver email: ");
	System.out.flush();
	String nombre = sc.nextLine();
	Boolean nombreEncontrado = false;
	for (Persona p: personas){
		if (nombre.equalsIgnoreCase(p.getNombre()) == true){
			System.out.println(p.getNombre());
			nombreEncontrado = true;
			break;
		}
	}
	if (nombreEncontrado == false){
		System.out.println("No existe nadie con ese nombre");
	}
	for (Persona p: personas){
		if (p.tieneArroba() == false){
			System.out.println("-- El siguiente usuario no tiene arroba:");
			p.imprimir();
		}
	}
	sc.close();
	}
}	
	
---
Persona.java
public class Persona {
	private String m_nombre;
	private String m_email;
	
	public Persona(String nombre, String email){
		m_nombre = nombre;
		m_email = email;
	}
	public String getNombre(){
		return m_nombre;
	}
	public void setNombre(String nombre){
		m_nombre = nombre;
	}
	public String getEmail(){
		return m_email;
	}
	public void setEmail(String email){
		m_email = email;
	}
	public void imprimir(){
		System.out.println("Nombre: " +m_nombre);
		System.out.println("Email: " +m_email);
	}
	public Boolean tieneArroba(){
		return m_email.contains("@");
	}
}
                                                            
                                                            
                                                            
