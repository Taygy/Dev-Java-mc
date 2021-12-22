# Dev-Java-mc

1. Commande sécuritaire pour savoir si le serveur est ouvert ou fermer. + Utilisation de Broadcast avec une commande /alert pour faire un message Générale a tous les joueurs. 

Liste des programmes servant a de multiples commandes dans MC


package fr.taygy.monplugin.commands; //nom de domaine a changer selon le votre

import org.bukkit.Bukkit;
import org.bukkit.command.Command;
import org.bukkit.command.CommandExecutor;
import org.bukkit.command.CommandSender;
import org.bukkit.entity.Player;

public class CommandTest implements CommandExecutor {

	@Override
	public boolean onCommand(CommandSender sender, Command cmd, String msg, String[] args) {
		
		//sender.sendMessage("Bravo ta reussit le test");
		  if(sender instanceof Player) {
			  Player player = (Player) sender;
			  
			  if(cmd.getName().equalsIgnoreCase("test")) {
				  player.sendMessage("§bBravo §9Champion");
				  return true;
			  }
			  if(cmd.getName().equalsIgnoreCase("alert")) {
				  
				  if(args.length==0) {
					  player.sendMessage("La commande est : /alert <message>");
				  }
				  if(args.length>=1) {
					  StringBuilder bc = new StringBuilder();
					  for(String part : args) {
						  bc.append(part + " ");
					  }
					  Bukkit.broadcastMessage("[" + player.getName() + "]§b §9 §b" + bc.toString());
					  //Objectif ; Reussir a ce que les differents arguments soient de differentes couleurs. 
				  }
				  return true;
				  
			  }

	        }
		return false;
	}
	

}
