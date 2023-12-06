---
title: Test
date: 2023-12-04
description: Simple test article
heroStyle: big
draft: false
showViews: true
showLikes: true
showComments: true

---

{{< typeit 
  tag=h3
  speed=50
  breakLines=false
  loop=true
    lifeLike=true
>}}
Yay, it works! 
This is very cool!
{{< /typeit >}}



![Cat gif](img/cat.gif)

---

Lets see how the charts look

## User population of selected internet browsers worldwide in 2021 (in millions)
{{< chart >}}
type: 'pie',
data: {
  labels: ['Chrome', 'Safari', 'Edge', 'Firefox', 'Opera', 'Internet Explorer',  'Other'],
  datasets: [{
    label: 'Millions of users',
    data: [3229.76, 576.85, 387.67, 362.18, 123.02, 69.1, 152.42],
  }]
}
{{< /chart >}}


Link to another article
{{< article link="/posts/markdown-syntax/">}}

{{< icon "github" >}} Github repo:
{{< github repo="brutehex/brutehex.tech" >}}

{{< timeline >}}

{{< timelineItem icon="github" header="header" badge="badge test" subheader="subheader" >}}
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus non magna ex. Donec sollicitudin ut lorem quis lobortis. Nam ac ipsum libero. Sed a ex eget ipsum tincidunt venenatis quis sed nisl. Pellentesque sed urna vel odio consequat tincidunt id ut purus. Nam sollicitudin est sed dui interdum rhoncus. 
{{< /timelineItem >}}


{{< timelineItem icon="code" header="Another Header" badge="1999 - present" subheader="Cool Subheader" >}}
With html code
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
{{< /timelineItem >}}

{{< timelineItem icon="star" header="Shortcodes" badge="AWESOME" >}}
With other shortcodes, like this gallery grid one with random images
{{< gallery >}}
  <img src="https://source.unsplash.com/random/600x400/?tech" class="grid-w33" />
  <img src="https://source.unsplash.com/random/600x400/?snow" class="grid-w33" />
  <img src="https://source.unsplash.com/random/600x400/?mountains" class="grid-w33" />
  <img src="https://source.unsplash.com/random/600x400/?man" class="grid-w33" />
  <img src="https://source.unsplash.com/random/600x400/?car" class="grid-w33" />
  <img src="https://source.unsplash.com/random/600x400/?cat" class="grid-w33" />
{{< /gallery >}}

{{< typeit 
  tag=h3
  lifeLike=true
>}}
Lorem ipsum dolor sit amet, 
consectetur adipiscing elit. 
{{< /typeit >}}
{{< /timelineItem >}}

{{< /timeline >}}

{{< chat test-brutehex >}}
