- [Home](/python/home)

# Nextcord menu dropdown 

Datum: 06/04/2022 
Tags: Python 
Téma: Dropdown menu 

```python 
import nextcord 
from nextcord.ext import commands 

class Dropdown(nextcord.ui.Select): 
    def __init__(self): 

    options = [ 

    nextcord.SelectOption(label="Label", description="description") 

    ] 
    super().__init__(placeholder="Text", min_values=1, max_values=1, options=options) 

    async def callback(self, interaction: nextcord.Interaction): 

    if self.values[0] == "Label": #placeholder in options 
    return await interaction.response.edit_message() #embed or meesage 

class DropdownView(nextcord.ui.View): 

    def __init__(self): 
    super().__init__() 

    self.add_item(Dropdown()) 

"""Some function""" 

view = DropdownView() 

await ctx.send(view=view) 
```
