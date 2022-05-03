# Basic bot 

Tags: Basics 

```python 
import nextcord 
from nextcord.ext import commands 

token = "your token here" 

bot = commands.Bot(command_prefix="!") 

@bot.event # prints ready when the bot is logged and ready to be used 
async def on_ready(): 
    print("ready") 

@bot.command() # registers command with name test 
async def test(ctx): 
    ctx.send("Hello world") 
    # sends text to the same channel 

bot.run(token) 
```
