---
layout: post
title:      "Level 1 in Data Science"
date:       2020-09-28 17:33:19 +0000
permalink:  level_1_in_data_science
---

Posted by Joe Sanchez September 28th, 2020

Almost 3 months into my coding bootcamp expierence and finally, i've finished my final project. However, only for the 1st module, out of 5. To sum up my experience, it has been one of best, if not thee best, learning experience i've ever had. 
I say that because there were many aspects to learning data science than just.. data science. I've learned coding not only from a student's perspective but from a business perspective as well, by taking on real world problems and scenarios. Learning data science was also a humbling experience. There were a few times that i had the mentality of, "This isn't that hard, i could it later" or "How hard could it possibly be to finish a section (part of the curriculum module)".
And boy did i have a hard time. Some sections were easy, others were not though. I guess i thought it wouldn't be that hard because of my past experience with coding. Which i will talk a little about, and how i continued my journey into coding.


I first got a taste of coding when i joined a computer science 101 class at my local community college. We learned a wide variety of things related to computer science and one part of that was learning code. Python in particular. Prior to that small python lesson, i had no experience with coding. "Knowingly" i should say. Because i was pretty good at editing my myspace page when i was a teen but i didnt actually know that i was coding at the time. To me it was a little copy and paste here and little modifications there. Anyways, other than that, code was pretty much new to me. But i ended up having a really good time with it, partially because i was very interested in how coding works. It kind of opened my mind up to what and how things work behind the scenes of a computer. It also helps that i naturally have a genuine interest in technology. After that my computer science class, i knew i wanted to try coding again but with a class that was more dedicated to learning code. A friend from work had mentioned a deal for a coding bootcamp. First time i ever heard of a coding bootcamp. After learning a little more of what that was, i signed up and joined a python coding bootcamp at codecademy. I loved it. It was an awesome experience and i feel like it opened up a new door of education for me that i could possilbe make a career out of. However i was not able to finish the course due to a personal matter. But luckily for me, i came across flatiron school a year later, and was able to continue my journey into coding and hopefully becoming a jr data scientist.

So here i am, as i mentioned at the beginning, at the end of my first final project. The project was a challenge. The most challenging part for me was, approaching and executing the project all on my own. I guess i was so used to being given directions on what to do through out the module 1 sections, that i was a little stuck when it came to me having to provide a solution on my own. I just had to remind myself that i know what to do. I mean i just learned a whole module and did countless lessons, its not like i don't know what to do! I believe it was just the whole "Where do i start" thing. I felt like at the beginning of the project i had that tattooed right on my forehead because it was only thing on my mind for awhile. But after taking a breather, i just started.. i just looked at the material that i had, i looked at my data and just went from there. I cleaned the data and tried to make sense of it, so that i can use it to come up with actionable insights. 

After going back and forth between cleaning data and looking at the project objective, my ideas started to gain traction and i started to perform data analysis and vizualizations. I found a rhythm. Questions came to mind about the project and my end results, and answers came to mind as well. So now that i had a solid direction in which i wanted to complete the project, i just had to make sure my coding was clean and that it worked. The biggest struggle that i had was converting dtypes from object to integer. I think i got too confused by all the solutions to do so on websites like 'stackoverflow' and 'careerkarma'. But i eventually figured it out, and i can show you here;

df_movie_budget['worldwide_gross'] = df_movie_budget['worldwide_gross'].apply(lambda x: x.replace('$',''))

df_movie_budget['worldwide_gross'] = df_movie_budget['worldwide_gross'].apply(lambda x: x.replace(',',''))

df_movie_budget['worldwide_gross'] = pd.to_numeric(df_movie_budget['worldwide_gross'], downcast='signed')

So here, im converting the column 'worldwide_gross' from the dataframe 'df_movie_budget', to a integer. 
Before these lines of code, df_movie_budget['worldwide_gross'] would run:

0    $2,776,345,279
Name: worldwide_gross, dtype: object

But after the lines of code it ran:

0    2776345279
Name: worldwide_gross, dtype: int64

Which is exactly what i needed to plot my graphs.

It took me a while to get that together but once i did, i knew i wasnt going to forget that!


To conclude this blog, i just want to say that, i'm very much looking forward to continuing on and learning more code. I'm surprised at how much i was able to learn in just one module, that i'm very excited to see what all i'll know by the end of the entire course. I do not regret my decision to do a data science bootcamp, not one bit, and i'm ready for the challenge ahead. I know it will not be easy, but sometimes you have to work hard to get where you want to be in life. 


