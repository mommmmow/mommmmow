import discord

client = discord.Client()

@client.event
async def on_ready():
    print(f"We have logged in as {client.user}")

@client.event
async def on_message(message):
    if message.author == client.user:
        return

    if message.content.startswith("!send"):
        channel = message.channel
        response = "Hello, I am your Discord bot!"
        await channel.send(response)

# Replace 'YOUR_BOT_TOKEN' with the bot token you copied earlier
client.run('YOUR_BOT_TOKEN')
