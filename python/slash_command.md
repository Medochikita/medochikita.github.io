# Nextcord slash command 

Tags: Slash command 

```python 
import nextcord 
from nextcord.ext import commands 

class SOME_COG(commands.Cog) 
    def __init__(self, bot): 
        self.bot = bot 

@nextcord.slash_command(name="", description="", guild_ids=[]) 
async def SOME_FUNCTION( 
    self, 
    interaction : nextcord.Interaction 
    arg : int = nextcord.Slashoption(description="", required=True/False) 
    ): 

    """Some function""" 

    await interaction.response.send_message("Text"/Embed/Dropdown) 
```
