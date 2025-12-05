# Nastro Bliss: Transforming Your Restaurant with AWS
*A strategic partnership bringing clarity, efficiency, and growth to your digital operations.*

## Restaurant Overview
Before we indulge into understanding the challanges that the resturant faced let us first understand the background of the resturant.
Nastro Bliss is a beloved restaurant situated at Johannesburg known for contemporary African cuisine and specializing in grill and fire menu items. Catering to local residence, corporate partners and to tourists to showcase their take and expertise in African cuisine.

## Operational Challenges
**Booking Confusion** - Reservation requests come through multiple channels like phone, walk-ins, social media. Information gets lost, double-booked tables create frustration.

**Order Mix-ups** - Orders placed verbally or via text lead to incorrect items, forgotten requests, and unhappy customers during peak hours.

**No Digital Presence** - Without an organized online platform, customers can't easily find menu information, hours, or availability hurting discoverability

Due to such challanges the business lost about:
- 30% of Lost Revenune
- 40% Staff Time Wasted
- 25% of customer satisfaction.

This did not put a good statement to the business as a whole.

## The Solution: A Static Website on AWS

A fast, good-looking static website hosted on AWS S3 with these features:
- Gallery of delicious dishes
- Dine-in reservation form
- Take-away / delivery order form
- Contact info and opening hours

Even though the front-end is static, everything that needs to be dynamic (forms, logins, storing bookings/orders) is handled by serverless AWS services – no servers to manage

## Project Walkthrough

We executed the project in two main phases: the development of a Static Website and the creation of an AWS Migration Presentation.

***Phase 1: Building and Deploying the Static Website***  

We designed and developed a clean, user-friendly static website for Nastro Bliss focusing on simplicity, visual appeal, and ease of navigation. We used minimal colors to enhance text readability and added interactive features such as a booking form, an order form, and a confirmation page.To make the website accessible online, we migrated it to Amazon S3, which we used to host all website assets, including images like menus and ambiance shots. We then integrated AWS CloudFront to enable fast, secure content delivery globally.  
In the end, we successfully deployed the fully functional website using Amazon S3, ensuring reliable hosting with high availability.

***Phase 2: AWS Migration Presentation*** 

I also created the AWS Migration Presentation, where I documented the migration plan, architecture, and business value of moving the restaurant’s digital experience to AWS. The presentation highlighted the problem, the solution, the services used, and the expected improvements in performance, reliability, and customer satisfaction.

## My Takeaways from the Static Website Project

Working on this project taught me a lot, especially as someone still new to web development and cloud computing. One of my biggest takeaways was learning how to design a clean, user-friendly website. I discovered that simplicity doesn't mean basic it means focusing on clear structure, ease of use, and making sure every element has a purpose. This helped me better understand how real users interact with websites, and how important layout and visual clarity are, especially when it comes to things like booking and order forms.

Another major learning point for me was deploying the website using Amazon S3. This was my first hands-on experience using a cloud service for hosting, and I gained confidence in uploading and managing website files in the cloud. It was exciting to see the site live and working properly after hosting it on AWS. I also learned how integrating CloudFront helps deliver content faster and securely around the world, which is something businesses rely on for performance.

Working with interactive elements like booking forms, order submissions, and confirmation pages helped me build more than just a static page it became a real, functioning site. I learned how these features improve user engagement and make the site more useful to visitors.

I also understood the importance of properly organizing assets such as images and HTML files in folders to keep everything structured. This made the website load faster and easier to maintain. Now I see how small technical decisions like compressing images or simplifying layouts contribute to overall performance.

In conclusion, this project helped me grow in both design thinking and technical execution. It gave me practical skills in using AWS, developing real-world web content, and thinking from the user’s perspective. I now feel more prepared and motivated to take on more advanced projects in the future.
## Team Members & Roles 
Lindokuhle.D -Research & Documentation

Ndzalo.M - Web Development & Functionality 

Chriswell.M - Deploying the website to S3

Thato.M - Research & Presentation

Palesa.N - Presentation 

