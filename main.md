# Dev-Java-mc

Voici mes recherches sur Java 16.0.2 et une version MC 1.17  

Voici ce que vous devais absolument avoir dans votre Main :  

package fr.taygy.monplugin;  // a changer selon votre nom de domaine

import org.bukkit.plugin.java.JavaPlugin;

import fr.taygy.monplugin.commands.CommandSpawn;
import fr.taygy.monplugin.commands.CommandTest;

public class Main extends JavaPlugin 
public class Principale extends JavaPlugin {
	
	private static Principale instance;
	public ArrayList<UUID> moderateurs = new ArrayList<>();
	public HashMap<UUID, PlayerManager> players = new HashMap<>();
	
	
	
	@Override// onEnable n'est pas reutilisable
	public void onEnable() {
		instance =this;
		 
	    System.out.println("Le plugin est ouvert !!");
	    getCommand("staffmod").setExecutor(new CommandStaffmode());
	    getServer().getPluginManager().registerEvents(new ParametreStaffMode(), this );
	      
	}
	

	
	@Override //
	public void onDisable() {
		System.out.println("Le plugin viens de s'eteindre"); 
	}



	public static Principale getInstance() {
		// TODO Auto-generated method stub
		return instance;
	}

}
