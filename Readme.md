# Git Tales

![Danger's lurking just behind you - though you might find it's just a nice tool.](/git-tales/assets/git-tales2.png){: width="200"}

Every day we're out here making *git tales* - These are some of the ever-fearless SmartGitty.


Hop on for a wild ride - there are a lot of branches to explore.

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
