# Bimbo bot blocklist

Since Elon Musk took over Twitter, I get likes from bimbo bots. I report them, I block them and Now I publish my blocklist in the hope it might be useful for you to block them too. 

## The list

Find my bimbo bot blocklist [here](./bimbobotblocklist.csv)

## What are bimbo bot accounts

Bimbo bots are bot accounts:

* that only like but do not engage in the conversation. (So far they didn't. Similar accounts on Facebook do.)
* They have no tweets, ar single tweet or few tweets of their own. 
* The account name is often a female first name followed by a number. It seems they cycle the names alphabetically
  If you get a like by a `Brenda<number>` then a next like will be by a `Brielle<otherNumber>`.
* Their profile often contains a link to adult entertainment or probably fake relationship websites.
* A few of those links immidiately redirect to Russian porn sites. I did not investigate further to get them blocked.
* that have a background picture that is often a tropical beach. They most likely contain some random noise to prevent blocking.
* The same original pictures are used over and over again.
* that have a profile picture that is often a lady in underwear or swimwear. More recently male or robot cartoons are used too.
  They most likely contain random noise to prevent blocking. Probably AI generated.
* The profile text or single tweet are randomized a bit by added emoji.


## Twitter's handling

* If you report these accounts, you quikly get a reply that what they do is not against their policies.
* Sometimes you get an update that they finally banned a single bot.
* The CSV import/export blocklist option from twitter does not exist any more.
* You can do an output of all your data including blocklist but that can take 24 hours
* You can register for a developer account. That will cost your $100 or you can ask for a free account.
  I wonder if and if so what kind of account these bimbo bots use?

I am certainly not going to pay $100. I will consider kindly asking for a free account at a later time. 

## Partially script  exporting your blocklist

First find out in the html source code of the X block list a node that contains te twitter handle of a bimbobot.
This probably is different on your account and may be different on a next login.

For me it was `css-15oi2r` and a few other classes.
I define a constant `elementClass` for that. We are going to build the blocklist in an array `ys`.
We get a `handle` on the current 'viewport' of the blocked bimbos with `xs`;

```JavaScript
const elementClass = 'css-175oi2r';
var ys = [];
var xs = document.getElementsByClassName(elementClass);

```

## Add all blocked bimbos to the list

Next move your browser to the top of your blocklist and execute the following script.
And execute the following script:


```
for(i=0;i<xs.length; i++) {s=xs[i].textContent;if (s.startsWith('@')) {ys.push(s);}}
```

Press `<PageDown>` and repeat the previous script. Press `<PageDown>` again and execute the script again. Continue until you reached the bottom of the page.


## Sort in place

```JavaScript
ys.sort()

```

## Deduplicate

```JavaScript
zs = [...new Set(ys)]
```

## Print the list

Print the set of blocked bimbos for further processing.

```JavaScript
zs.forEach(z => console.log(z);)
```

## Future work

The following is an exercise for the reader :) :

* Automate the the scrolling
* Add a save to file option
* Add an import option


