# Dev-Java-mc

Voici mes recherches sur Java 16.0.2 et une version MC 1.17  

Voici ce que vous devais absolument avoir dans votre Main :  

package fr.taygy.monplugin;  // a changer selon votre nom de domaine

import org.bukkit.plugin.java.JavaPlugin;

import fr.taygy.monplugin.commands.CommandSpawn;
import fr.taygy.monplugin.commands.CommandTest;

public class Main extends JavaPlugin {
	
	@Override
	public void onEnable() {
		System.out.println("Le plugin viens de s'allumer");
		getCommand("test").setExecutor(new CommandTest());
		getCommand("alert").setExecutor(new CommandTest());
		getCommand("spawn").setExecutor(new CommandSpawn());
		getServer().getPluginManager().registerEvents(new MonPluginListeners(), this );
		
	}
	@Override
	public void onDisable() {
		System.out.println("Le plugin viens de s'eteindre"); 
	}

}
