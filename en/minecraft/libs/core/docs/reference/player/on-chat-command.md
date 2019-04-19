# on Chat Command

Runs code when you type a certain message in the game chat. You can also add extra information to the command as *arguments*.

```sig
player.onChat("jump", function () {});
```

You make a command by giving it a command name like "bigjump". If you wanted the "bigjump" command to allow you to say the distance for the jump, you could add one or more values in the command to tell where and how far to jump.

### Parameters

* **command**: the chat keyword that will be associated with this command (`*` for all messages), eg: "jump"
* **handler**: code to run when the keyword is typed in the chat by the current player

### Example

This command makes the player jump very high when `jump` is typed in the chat.

```blocks
player.onChat("jump", function () {
    player.teleport(positions.create(0, 10, 0));
});
```

## Advanced: Arguments

You can add arguments to your chat commands. The code running in the chat command can use these arguments to do all sorts of fun things. To add arguments to a chat command, click the **"+"** icon in the top-right corner of the `||player:on chat command||` block.

For example, the following chat command takes a number as an argument:

```blocks
player.onChat("command1", function (num1) {

});
```

Chat commands can take more than one argument. You can use up to **three** arguments that are numbers you type in the chat.

You can use arguments to customize the code in your chat command - your imagination is the limit! The following chat command takes multiple arguments:

```blocks
player.onChat("command2", function (num1, num2, num3) {

});
```

### ~ hint

**Just use numbers**

The arguments have to be numbers. If the "bigjump" command uses one argument, then it's typed in the chat like this:

    bigjump 50
    

### ~

### ~ hint

**Renaming the arguments**

When you add arguments, they are automatically named **num1**, **num2** and **num3**. You can give them more descriptive names by clicking on them in the `||player:on chat command||` block, and selecting **Rename variable...** in the menu.

```blocks
player.onChat("rectangle", function (width, height) {

});
```

### ~

### Example

This command modifies the jump example above. It lets the player decide how high they want to jump by taking a number argument and using it in the teleport destination. To use this chat command, the player would type `jump 10` in the game chat. Want to jump even higher? Type `jump 100`!

```blocks
player.onChat("jump", function (height) {
    player.teleport(positions.create(0, height, 0))
})
```