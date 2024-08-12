# Cain for Foundry

This repo contains the world/files/templates for the CSB system for [CAIN created by Tom Bloom](https://tombloom.itch.io/cain).
Have questions? You can reach out to me @calicoskunk on PNET or the unofficial CAIN discord.

## Use

This module is intended for use with the [Custom System Builder](https://foundryvtt.com/packages/custom-system-builder/) System. It will not work in other systems.

Once you have installed the module and its compendia, make sure you do the following:

1. Go to the Compendium Items tab in Foundry.
2. Right click on each of the added compendia, and import all content (with the "Keep Document IDs" checked to true).
3. Done! If an update does come out, simply do this again.

**IMPORTANT:** After importing, its a good idea to reload all character sheets (if you're updating).

![image](https://github.com/user-attachments/assets/141e5cd2-b2ac-4bd0-befc-2cea6b67c73f)

## Creating a character

1. Create a new actor as normal.

![image](https://github.com/user-attachments/assets/9e74a8e2-74d9-4454-98ef-8d80609695ac)

2. Once open, make sure the dropdown is set to `_Exorcist`, then hit the refresh button.

![image](https://github.com/user-attachments/assets/65a8d81e-3a94-48fd-b694-0659029d9486)

Done.

### Adding Agendas to a sheet

1. Create a new item in the items tab with the `equippableItem` type.
2. Make sure that the dropdown is set to `_Agenda`, then refresh the item.
3. Customize as required. You can create new items with the `_AgendaAbility` type and drag them into the "Abilities" text area for easy access. (**Note:** These are the items that contain automation. Check out the below section for more information.)

This is an example of a finished Agenda (the "Make Item Unique" checkbox makes it so players can only equip one copy of that agenda/item):

![image](https://github.com/user-attachments/assets/60dd0516-9e31-48ef-99fa-fee1f9eb84ef)

4. Drag the Agenda anywhere onto your sheet.

It should look like this when you are done:

![image](https://github.com/user-attachments/assets/9607c690-adcc-481f-aa28-be9106db5801)

**Note:** Because of the nature of "bolded agenda items" and their overhead, I've left it as a "add as you will" type system.
To add a "bolded agenda item", click on the `+` symbol on the far right of the table and input your bolded item manually.

![image](https://github.com/user-attachments/assets/6c55375c-0e11-422f-97e1-0b413584e27b)

### Agenda Abilities

Agenda abilities are extremely simple. They contain a Description field and nothing else. To achieve automation from an agenda ability, you'll need to open the `_Exorcist` template in the actors tab. This is the base sheet that all players use for their exorcists. Some values are contained within number field inputs (such as number of blasphemies, `numblasphemy`), and others are hidden at the top of the page, "Configure hidden attributes".

Here is an example of creating a simple agenda abilitiy that increases maximum stress on the execution talisman by 1.

1. Find the max stress value. In this case, we can see it both displayed on the sheet near the execution/stress input box, and contained from within the hidden properties tab: `maxstress`.
2. Create a new agenda ability item, give it a description (optional), then press the "Configure item modifiers" button.
3. In this menu, press the `+` button under the "item modifiers" table.
4. Place your variable name under the `key` column. In this case, `maxstress`.
5. `Op` is the operation that the modifier performs. In this case, we want `+`.
6. Variable formula will be the number included by the operator. In our case, its `1`.
7. Description optional, but I usually like to include the decsription of the ability.

For more complex options, you will have to either submit a feature request or implement it yourself. By default, CSB only supports number modifications.
There is an example of an "advanced" item modifier in the hidden attribute `ignoreinj`. The `Painkiller` agenda modifies the value by 1. In the `maxstress` hidden attribute there is a condition that checks for it, and disables adding injuries if the `ignoreinj` value is not 0.

**Note:** Any alterations to the template are subject to deletion upon any template update.
