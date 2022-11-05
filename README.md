# Obsidian-Snippets

Hello! I've never used GitHub before so bear with me. So far, I have only one snippet to share, but I'm hoping to test more for others to use. Let me know if you have any problems and I'll see what I can do.

> I use S1Rvb's [ITS theme](https://github.com/SlRvb/Obsidian--ITS-Theme), but these snippets should work with light themes, too. You'll need to edit the colours, but there's nothing stopping you from customising your highlighter palette, anyway.

## Labelled Highlighters

Have a bunch of highlighter colours for different purposes but can never remember what colour to use? Going over your notes and forgotten what a pink highlighter was for? Want to highlight a text as a reminder to check your spelling, or to edit a paragraph, etc?

This snippet lets you customise the colours of your highlighters _while telling you what it's for_. 

<img width="712" alt="Screenshot 2022-11-05 at 11 43 47" src="https://user-images.githubusercontent.com/115729056/200118253-e38c2f4d-2970-4dbb-8d4f-88b1857e29f2.png">

> There is a highlighter plugin that does more or less the same thing, but the code is longer than it really needs to be and creates noise in your notes. I wanted something similar but that wouldn't add unnecessary text.

### What you'll need to make it work

Unfortunately, you can't just use the built-in Obsidian highlighter `==` for this, you need to use HTML, e.g. `<mark class="red">Your highlighted text</mark>`. You _could_ type this all out yourself, but I use a template. 

- [Templater plugin](https://github.com/SilentVoid13/Templater)
- [highlighters.css](https://github.com/soggymuse/Obsidian-Snippets/blob/main/highlighters.css)
- [Highlighter Template](https://github.com/soggymuse/Obsidian-Snippets/blob/main/Highlighter%20Template.md)

### Installation

1. Make sure you have [Templater plugin](https://github.com/SilentVoid13/Templater) installed and enabled.
2. Download [highlighters.css](https://github.com/soggymuse/Obsidian-Snippets/blob/main/highlighters.css) and save it to your snippets folder (your Obsidian `vault > .obsidian > snippets`).
3. Copy the [Highlighter Template](https://github.com/soggymuse/Obsidian-Snippets/blob/main/Highlighter%20Template.md) to your Obsidian templates folder.

### How to use labelled highlighters in your notes

1. Write your text.
2. Select the text you want to highlight.
3. Type CMD+T to open your Templater modal (a drop-down list of templates). 
4. Start typing `hig` and the selection should quickly narrow down.
5. Choose your Highlighter template. The result should be `<mark class="red">Your highlighted text</mark>`

> ### Alternative Use
> If you, like me, can't make `<% tp.file.selection %>` work, an alternative method is to edit [Highlighter Template](https://github.com/soggymuse/Obsidian-Snippets/blob/main/Highlighter%20Template.md) so all it says is `<mark class="red">`, then insert that in front of your highlighted text. You'll then need to type the following _after_ your highlighted text: `</mark>`. It's a PITA but it's how I use my highlighters.
> 
> The benefit of _this_ method is that, while it means more typing, you only need the core Templates plugin and not the additional [Templater plugin](https://github.com/SilentVoid13/Templater) (although I highly recommend it anyway).

> ### Using Multiple Templates
> If you're too ~~lazy~~ busy to change `red` every time you insert a highlighter, you could copy [Highlighter Template](https://github.com/soggymuse/Obsidian-Snippets/blob/main/Highlighter%20Template.md) a bunch of times, edit `.red` for each one, and rename them so you can insert each template as needed.  

### Customising your Highlighter Colours

1. Open `highlighters.css` in a plain text editor.
2. Replace the hex codes for `color` and `border-bottom-color` to suit.
3. You can also change the label where it says `content`. Make sure to surround your chosen label with quotation marks `"`.

#### Adding more highlighters

If six highlighter colours aren't enough, you can add more!

1. Copy the code below and edit `Red` and `.red` to a colour not already listed.
2. Change `color` and `border-bottom-color` to suit.
3. Change the label as you like by editing `content`. Make sure to surround your label with quotation marks `"`.

```
/*Red highlighter (edit)*/
.markdown-rendered mark.red,
.cm-s-obsidian span.cm-html-embed mark.red { 
	border-bottom-color: #7D3B56; }
	
.markdown-rendered mark.red::before,
.cm-s-obsidian span.cm-html-embed mark.red::before {
    content: "To edit:"; 
    color: #7D3B56; }
```

## Labelled Highlighters on Hover

This is the same as my Labelled Highlighters, but instead of having a permanent label, you can only see the highlighter's category _when you hover over it_.

<img width="710" alt="Screenshot 2022-11-05 at 14 22 29" src="https://user-images.githubusercontent.com/115729056/200124571-e9d07207-4f9e-4ecf-a250-7b9bddea1405.png">

_before hovering over the highlighted text_

Refer to the instructions for **Labelled Highlighters** to use this snippet, but download `highlighters-hover.css` instead of `highlighters.css`. The rest is basically the same.

<img width="712" alt="Screenshot 2022-11-05 at 14 22 41" src="https://user-images.githubusercontent.com/115729056/200124577-ea9fcbbd-d471-452c-b437-d9dd8524be03.png">

_after hovering over the highlighted text_

## Contributions

- Thanks to [MelchiorBV](https://discordapp.com/users/810537814693249034) for the [heads-up](https://discord.com/channels/686053708261228577/744933215063638183/1036351441390018601) on using `tp.file.selection`!
- Thanks to [TheTobruk](https://discordapp.com/users/1036215418983026709) for the reminder that live preview requires a different code 😅
