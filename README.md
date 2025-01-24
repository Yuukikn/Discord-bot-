# Discord-bot-

My attempt at making a discord bot to help people in my channel to find info on a game i used to play i tride with a prefex at first but even with a page to show how to use the bot people never looked to find out
so i changed the prefex to try and just read messages from certain key words.

import discord
import logging
from discord.ext import commands

level = ["level", "leveling", "boss", "bosses"]
blacksmith = ["refine", "refinement", "stat", "stating",
              "blacksmith"]
food_buffs = ["how", "were", "buff", "guide"]
materials = ["mana", "wood", "cloth", "medicine ", "meds", "beast", "metal"]
builds = ["archer", "bow", "bow gun", "bowgun", "tank", "knuckles", "paladin", "katana", "bowtana", "dual wild", "dw",
          "magic warrior", "mage", "halberd", "magic device", "md", "sprite", "crusher", "assassin", "2h", "2 hand"
          "two hand"]
guild_raid = ["what", "whats", "what's", "were", "how", "weres", "were's", "raid", "raids"]
pet_tamer = ["how", "were", "train", "training", "raise", "catch", "capture", "discipline", "skill", "skills", "guide",
             "guides"]
spina = ["spina", "money"]
alchemy = ["synth", "synthesis", "lock", "dye"]
smith_alch = ["pot", "potential", "proficiency", "prof", "craft", "crafting"]

words = ["how", "were", "guide", "what", "whats"]

leveling_guide = channel_location
stating_guide = channel_location
refining_guide = channel_location
bs_prof = channel_location

handler = logging.FileHandler(filename='genral.log', encoding='utf-8', mode='w')

botToken = bot_token
testChannelNumber = channelNumber

bot = commands.Bot(command_prefix="", intents=discord.Intents.all())
intents = discord.Intents.default()
intents.messages = True

client = discord.client


@bot.event
async def on_ready():
    @bot.event
    async def on_message(message):
        key_level = False
        key_smith = False
        key_food = False
        key_materials = False
        key_build = False
        key_tamer = False
        key_spina = False
        key_synth = False
        key_craft = False

        if not discord.utils.get(message.author.roles, name='bot'):

            if "credit" in message.content.lower():
                await message.channel.send("The ones who made this guild possible from guide, bots and more thank you!"
                                           " names!")

            if ("level" in message.content.lower() or "leveling" in message.content.lower()
                    or "boss" in message.content.lower()) or "bosses" in message.content.lower():
                key_level = not False

            if key_level is True:
                for word in words:
                    if word in message.content.lower():
                        await message.channel.send(f"Here is a leveling guide {leveling_guide} made by name. potum!"
                                                   "\nThis link may help too potum! "
                                                   "\nhttps://coryn.club/leveling.php?|v= ")
                        message.content.delete()
                        break

            if ("what" in message.content.lower() or "how" in message.content.lower() or "guide" in message.content.
                    lower() or "formula" in message.content.lower()):
                key_smith = not False

            if key_smith is True:
                for word in blacksmith:
                    if word in message.content.lower():
                        await message.channel.send(f"Here is some guides for blacksmith potum!: "
                                                   f"\nRefining: {refining_guide} "
                                                   f"\nStating: {stating_guide} "
                                                   f"\nMade by names"
                                                   f"\nThis links may help to potum!"
                                                   f"\nGuide: https://coryn.club/guide.php?key=smith"
                                                   f"\nStatting sim: https://coryn.club/statting_simulator.php"
                                                   f"\nSearch for formulas: https://coryn.club/formula_search.php"
                                                   f"\nStatting formulas: https://coryn.club/formula.php")
                        message.content.delete()
                        break

            if "food" in message.content.lower():
                key_food = not False

            if key_food is True:
                for word in food_buffs:
                    if word in message.content.lower():
                        await message.channel.send("Here is some food buff addresses and "
                                                   "channel_link"
                                                   " potum! ")
                        message.content.delete()
                        break

            if ("were" in message.content.lower() or "how" in message.content.lower() or
                    "materials" in message.content.lower() or "locations" in message.content.lower()):
                key_materials = not False

            if key_materials is True:
                for word in materials:
                    if word in message.content.lower():
                        await message.channel.send("Here is some material farming spots "
                                                   "channel_link"
                                                   "potum!"
                                                   "\nMade by name")
                        message.content.delete()
                        break

            if "guild" in message.content.lower():
                key_build = not False

            if key_build is True:
                for word in guild_raid:
                    if word in message.content.lower():
                        await message.channel.send("Here is a guide to guild raids: "
                                                   "chennel_link"
                                                   "potum!")
                        message.content.delete()
                        break

            if ("pet" in message.content.lower() or "tamer" in message.content.lower() or
                    "tam" in message.content.lower() or "taming" in message.content.lower()
                    or "pets" in message.content.lower() or "what" in message.content.lower()
                    or "whats" in message.content.lower()):
                key_tamer = not False

            if key_tamer is True:
                for word in pet_tamer:
                    if word in message.content.lower():
                        await message.channel.send("This is  a guide may help "
                                                   "channel_lonk"
                                                   " potum!"
                                                   "\nThese links may help to"
                                                   "\nGuide: https://coryn.club/guide.php?key=petguide"
                                                   "\nStat calculator: https://coryn.club/pet_calculator.php"
                                                   "\nPet leveling: https://coryn.club/pet_leveling.php"
                                                   "\nPet fusion: https://coryn.club/pet_fusion_optimizer.php")
                        message.content.delete()
                        break

            if ("how" in message.content.lower() or "what" in message.content.lower()
                    or "guide" in message.content.lower() or "build" in message.content.lower()
                    or "builds" in message.content.lower()):
                key_build = not False

            if key_build is True:
                for word in builds:
                    if word in message.content.lower():
                        await message.channel.send("Here is some build guides that may help potum! "
                                                   "channel_link"
                                                   "channel_link"
                                                   "\n channel_link"
                                                   "channel_link")
                        message.content.delete()
                        break

            if ("how" in message.content.lower() or "were" in message.content.lower()
                    or "farm" in message.content.lower() or "farming" in message.content.lower()):
                key_spina = not False

            if key_spina is True:
                for word in spina:
                    if word in message.content.lower():
                        await message.channel.send("channel_link"
                                                   "chennel_link")
                        message.content.delete()
                        break

            if "how" in message.content.lower() or "what" in message.content.lower():
                key_synth = not False

            if key_synth is True:
                for word in alchemy:
                    if word in message.content.lower():
                        await message.channel.send("channel_link"
                                                   "chennel_link"
                                                   "\nMade by name"
                                                   "\nThese links may help too"
                                                   "\nSynthesis sim: https://coryn.club/app_simulator.php"
                                                   "\nDye finder: https://coryn.club/dye_finder.php")
                        message.content.delete()
                        break

            if "how" in message.content.lower() or "what" in message.content.lower():
                key_craft = not False

            if key_craft is True:
                for word in smith_alch:
                    if word in message.content.lower():
                        await message.channel.send("This may help potum!"
                                                   "channel_link"
                                                   "channel_link"
                                                   "channel_link"
                                                   "chennel_link"
                                                   "Made by names"
                                                   "These links may help too"
                                                   "\nBlacksmith craftable items: https://coryn.club"
                                                   "/item.php?special=psmith&order=level"
                                                   "\nAlchemy craftable items: https://coryn.club/"
                                                   "item.php?special=palch&order=level")
                        message.content.delete()
                        break

bot.run(botToken, log_handler=handler)
