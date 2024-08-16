# Verilock
[Source Code](https://github.com/larryr1/verilock)

Verilock is a Minecraft Java server plugin (Built for the [Paper](https://papermc.io) server software, a fork of [Bukkit](https://dev.bukkit.org)) which forces players to authenticate to the server with their student ID and birthday. Verilock was created to assist with securing a school-sponsored Minecraft server I was in charge of managing, where only verified students were allowed to play.

This project is the first large Java project I've kept up with, which has taught me a lot about the language and how Java projects are developed. After developing this and a few other small Java projects, I can say that I enjoy using it.

Usage of the plugin is simple. First, you run a report in your Student Information System (SIS) that generates a CSV file with the expected schema. Then, you drop the CSV file into the folder that got generated for the plugin. After adding the file, you run a command in-game which makes the server parse the file.

The plugin maintains a SQLite database, with a table for all the records you imported from the file and a table for all the players that have verified. When a player tries to verify, the plugin queries the database for a student record with the matching ID and birthday. If found, a record is created for the player in the players table marking you as verified.

The plugin also integrates with the most popular Bukkit permissions plugin, [LuckPerms](https://luckperms.net), so you can give players different in-game permissions depending on if they are verified or not.

The plugin also allows you to perform database operations in-game via commands.
```
/verilock reload - Reloads certain features of the plugin for quick testing.
/verilock identities import - Starts the import from the CSV file you generated.
/verilock database lookup_player <player> - Looks up a player in the database and tells information about them, including their student record if they are verified.
/verilock database lookup_identity <id> - Looks up a student record in the database with a specified student ID. If a player is linked to this ID, it also tells information about the player.
/verilock database link_identity <player> <id> - Manually links a player to the specified ID.
/verilock database unlink_identity <player> - Manually unlinks the specified player from any student record.
```
## Video demo
This video shows what it looks like from a user's perspective, with joining for the first time and subsequent joins after that.

[Verilock Demo Video](https://larryr1.github.io/projects/verilock/verilock_demo.mp4)
