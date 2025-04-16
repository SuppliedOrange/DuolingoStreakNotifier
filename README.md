#### Cloned from my original post: https://forum.kustom.rocks/t/duolingo-streak-helper-widget-with-discord-notification-support/7144

##### From March 2, 2024, 3:25am

This repository contains a _Kustom Widget File_ in it's releases. You can open this file with the [Kustom Widget](https://play.google.com/store/apps/details?id=org.kustom.widget&)
app for Android. Note that you will likely need to donate to the app to unlock the ability to import this file. Additionally, you can simply ask me for the code and I'll gladly
show you the parts of it or help you understand parts of it.

The documentation for Kustom is here: https://docs.kustom.rocks/docs/reference/functions/

# Duolingo Streak Notifier

This widget displays:

- Your current Duolingo Streak (which changes color depending on how high it is)
- The time till your next streak begins or ends
- Whether or not you’ve finished the streak today
- Optionally sends you a message on Discord through a webhook at a certain hour of day of your choice if you haven’t completed your streak yet.

### Here’s what mine looks like right now:

![Screenshot_20240302-074351](https://forumcdn.kustom.rocks/original/2X/7/7ecf47cb341847eecfb13222f55358ea0ca52031.webp)

### Here’s what the Discord notification looks like:

![Discord Notification](https://forumcdn.kustom.rocks/optimized/2X/b/b600332a104aa8316321d270a46f0a787c374462_2_690x170.png)

### Here are two screenshots displaying when a streak is finished or unfinished:
![Streak Finished](https://forumcdn.kustom.rocks/optimized/2X/b/bc8a955cc393f71ef1254f9dc85dc1528780bb97_2_225x500.jpeg)
![Streak Unfinished](https://forumcdn.kustom.rocks/optimized/2X/3/3bd8f463561b6d73a92dd4054d98b20d8b8ccde0_2_225x500.jpeg)

This widget is themed according to the rest of my Nothing Phone. I encourage you to salvage parts of this komponent and use it for yourself. If you wish to see the code for something, let me know and I’ll tell you how I did it.

---

### Duolingo’s API:

Duolingo has an undocumented API (there are many unofficial APIs that attempt to document it). You can access the link I mentioned below while logged in (gives you a lot more data) or you can access it anonymously, which still gives you enough data to do what I did. You might want to Google to learn more if you’re interested since this is all I know.  
API Link: https://duolingo.com/2017-06-30/users?username=YourUsernameHere

### How are you checking if the streak is completed?

This certain parameter in their JSON:  
`.users[0].streakData.currentStreak.endDate`
This parameter tells you the last time you participated in the streak. If this date is lesser than the current date, you have yet to participate in your streak today, hence incomplete. I am still unsure what happens if there’s no streak, but there are fallbacks for that which should hopefully work.

### Discord Notifications:

You will have to set a few globals before this works:

- Set your webhook URL. This will send messages in that channel as long as the webhook is active.
- Set the hour you would like this to trigger if unfinished (24-hour). 17 by default.
- Set your Discord user ID (not username) optionally if you would like to be pinged by the webhook.

Note that this is not very well tested and might bug out; feel free to improve it.

---

I am new to Kustom and criticism is appreciated.

Install widget: [36.2 KB file on MEGA](https://mega.nz/file/6YwTXQYC#heXsg-ycu1HcQfipQKC_veFgpvCQRQZfkxhm5DY6ZaE)

Or install from the [releases tab](https://github.com/SuppliedOrange/DuolingoStreakNotifier/releases/latest)
