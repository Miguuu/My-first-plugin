# My-first-plugin

<?
namespace Miguu\Prueba;

use pocketmine\plugin\PluginBase;
use pocketmine\command\Command;
use pocketmine\command\CommandSender;
use pocketmine\event\Listener;
use pocketmine\Player;

class Main extends PluginBase { 

    protected function onEnable() : void{  
        $this->getLogger()->info("Plugin has been Enabled");
        $this->getServer()->getPluginManager()->registerEvents(new EventListener(), $this);
    }
    public function onCommand(CommandSender $sender, Command $cmd, string $label, array $args) : bool{
    switch($cmd->getName()){
        case "lore":
        $name = $sender->getName();
        if($sender->hasPermission(prueba.command.lore)){
        	if(!$sender instanceof Player){
        	$sender->sendMessage("Gilipollas, esto solo funciona en el juego");
        }
            $sender->sendMessage("Lore," . $name . "te ama");
}
return false;
}
}
}
?>


