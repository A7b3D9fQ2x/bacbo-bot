# PimentelKing-discord 
import discord
from discord.ext import commands
import os

TOKEN = os.getenv("0dc1c9d10c1daeae3b692c1eb14333db617a56679d6b95f45da0e288d636ee11")

intents = discord.Intents.default()
bot = commands.Bot(command_prefix="!", intents=intents)

greens = 8
reds = 2
greens_seguidos = 4

@bot.event
async def on_ready():
    print(f"✅ PimentelKing está online como {bot.user}")

@bot.command()
async def placar(ctx):
    taxa = round((greens / (greens + reds)) * 100, 2)
    await ctx.send(f"""
📊 Placar do Dia: 🟢 {greens} 🔴 {reds}
🎯 Acertividade: {taxa}%
👑 PimentelKing está com {greens_seguidos} Greens Seguidos
""")

bot.run(TOKEN)


