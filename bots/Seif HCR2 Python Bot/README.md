# [Botpedia](/README.md) - [Seif HCR2 Python Bot](/bots/Seif%20HCR2%20Python%20Bot/README.md)

## Introduction
[Seif HCR2 Python Bot](/bots/Seif%20HCR2%20Python%20Bot/README.md) was a bot made by [Seif](/developers/Seif/README.md), an infamous Discord bot developer, who has made quite a lot of bots themselves.

The bot's purpose is unclear, but it is likely something to do with the infamous game of `Hill Climb Racing 2 (HCR2)`, which is likely where the name stemmed from.

## Source Leak
On the 26th of August 2024, a (now deleted) source code leak of [Seif HCR2 Python Bot](/bots/Seif%20HCR2%20Python%20Bot/README.md) was spotted within a Discord server under the name of `Dires Hosting`, and was spotted by a developer under the name of [Zayaan AR](/developers/Zayaan%20AR/README.md) in the `general-chat` channel of the server.

The source code aforementioned is displayed here:

```python
@bot.command()
@commands.has_permissions(ban_members=True , kick_members=True)
async def rule5(ctx):
        embed = discord.Embed(title="Rule 5",
                      description="No trolling or harassment: Harassment of any kind will not be tolerated and may result in an immediate ban from the server. Use appropriate language",
                      colour=0x00b0f4,
                      timestamp=datetime.now())
        
        embed.set_author(name="Seif HCR2 Python Bot",
                 icon_url="https://cdn.discordapp.com/icons/1184096475626618901/a_e89490ac4d874bb8c8795177e5e65026.gif?size=1024&width=0&height=384")

        await ctx.send(embed=embed)`
or this? `@bot.command()
@commands.has_permissions(moderate_members=True)
async def timeout(ctx, member: discord.Member, minutes: int, *, reason: str = "No reason provided"):
    # Define duration at the beginning to ensure it's available throughout the function
    duration = datetime.timedelta(minutes=minutes)

    if ctx.author.top_role <= member.top_role:
        await ctx.send("Can't timeout that user because their role is higher or equal to yours.")
        return  # Exit the command if the role check fails

    end_time = datetime.datetime.utcnow() + duration
    logs_channel = discord.utils.get(ctx.guild.channels, name='logs')

    try:
        await member.timeout(duration, reason=reason)
        await ctx.send(f'Timed out {member}#0 for {minutes} minutes successfully! Reason: {reason}.')
        try:
            await member.send(f"You've been timed out from {ctx.guild.name} for {minutes} minutes. Reason: {reason}")
        except discord.Forbidden:
            await ctx.send(f"Failed to send a direct message to {member}#0. They may have blocked the bot or disabled DMs.")
    except discord.Forbidden:
        await ctx.send("I don't have permission to timeout that user.")
```

The source code leak led to the discovery of this bot as a whole, and contains valuable information, like the profile picture of the bot, the name of the bot, along with other vital details about what the bot was like when it was in use.

## Summary
Speculation has lead to this bot offically being classified on [Botpedia](/README.md) as `unknown, likely deleted`, due to the fact that we are unable to find any userIDs linked to this bot, and that [Seif](/developers/Seif/README.md) hasn't commented on the situation, and until we recieve an update on this, the classification of this bot will stay as is.