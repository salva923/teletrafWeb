---
title: 'The two umbrellas'
description: 'This is a simple problem to review basic concepts of dtmc '
pubDate: 'Jun 02 2024'
heroImage: '/umbrella.avif'
---
An Individual possesses a total of n
 umbrellas that she uses in going from his home to his office, and vice versa.

If she is at home (at the office) at the beginning (end) of a day and it is raining, then he will take an umbrella when travelling to the office (to home) provided there is one to be taken.

If it is not raining, then he never takes an umbrella.

Assuming that, independent of the past, it rains at the beginning (end) of each a day with probability p, what are the chances of getting wet 

<object data="/umbrella.pdf" type="application/pdf" width="700px" height="700px">
    <embed src="/umbrella.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="/umbrella.pdf">Download PDF</a>.</p>
    </embed>
</object>


Here it is the matlab script that calculates the probability(You can find the copy in git repository):
```
%Umbrela simulation$
clear
clc
p=0.3%Raining probability change it depending of the problem

P=[(1-p),p,0;p*(1-p),(1-p)^2+p^2,(1-p)*p;0,p*(1-p),1-p*(1-p)]%Tansition matrix
n=50000;%number of days
P_n=P^n;
X_n=transpose(P_n(1,:))%Stationary probability.

P_wet=p*X_n(1)+p*X_n(3)%Prob. of getting wet is that it rains in the evening with all the umbrellas at home or
% it rains in the morning with all the umbrellas at the office

```