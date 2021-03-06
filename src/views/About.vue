<template>
    <div class="about-container">
        <article class="ng-scope">
        <h2>About Us</h2>
        <p>
            The Association for Computing Machinery is the largest and oldest international scientific and educational computing society in the industry today.
            The ACM is dedicated to advancing the art, science, engineering, and application of information technology.
            The BYU chapter is just one of many student chapters throughout the United States.
            You can view our bylaws <a href="static/bylaws.pdf" target="_blank">here</a>.
            Our vision for the BYU chapter of ACM is:
        </p>
        <p><b>
            "Enhancing our university experience through Networking, Education and Service"
        </b></p>
        </article>

        <article class="ng-scope">
        <h2>Networking</h2>
        <p>
            ...as in people networking.
            This aspect of our vision includes getting to know representatives from local and international companies, the faculty here at BYU and other universities and each other!
            Activities include:
        </p>
        <p>
            Tech Talks: Presentations from faculty and industrial sponsor representatives.
        </p>
        <p>
            Job Openings: Career placement presentations.
        </p>
        <p>
            On-on-one: Resume reviews and the recruitment dinner give you more one-on-one time with recruiters.
        </p>
        </article>

        <article class="ng-scope">
        <h2>Education</h2>
        <p>
            This is why we're here at BYU, right?
            But beyond the learning we do in the classroom, there are other topics that are important to helping us transition into the workplace.
            Plus, it's fun to learn cool stuff!  Activities include:
        </p>
        <p>
            Tech talks covering subjects such as machine learning, big data, and technologies used in the real world as well as the soft skills required to get the job that you want.
        </p>
        <p>
            Programming Competitions:
            At least once per semester, we have a four hour coding competition.
            Check our events tab for more information!
        </p>
        <p>
            Hackathons: During Winter Semester we will host a 24-hour hackathon.
        </p>
        </article>

        <article class="ng-scope">
        <h2>Service</h2>
        <p>
            We are all blessed with talents and abilities and now BYU ACM is providing opportunities to use those to help others!
        </p>
        <p>
            ACM helps host “Discover STEM”, a middle school career fair at BYU.
            We also are always looking for opportunities to tutor and help all students, especially minorities and those K-12 get involved with computer science.
        </p>
        </article>

        <article class="ng-scope">
        <h2 id="paying_club_dues">Paying Club Dues</h2>
        To pay club dues, please go the the <a href="https://commerce.cashnet.com/webc?itemcode=webc-acmd" target="_blank">BYU Student Organizations website</a>, sign in, and request to join club.

        We will be checking that you've paid club dues at the door to the Recruitment Dinner.
        </article>

        <article class="ng-scope">
        <h2>Contact Us</h2>
        <p>
            Companies: Please email <a href="mailto:acm@byu.edu">acm@byu.edu</a> and put your company's name and the name of our networking lead, {{networking_officer}}, in the subject line.
        </p>
        <p>
            Students: Contacting the ACM Slack account, <a href="https://byucompsci.slack.com/messages/D90FCBFMZ/" target="_blank">@ACM Club</a> at <a href="https://byucompsci.slack.com" target="_blank">byucompsci.slack.com</a> will probably be faster than emailing <a href="mailto:acm@byu.edu">acm@byu.edu</a> (but you can do either).
        </p>
        <p>
            Professors: If neither Slack nor email work for you, our faculty advisor is Dr. Frank Jones and you can contact him <a href="mailto:frjones@cs.byu.edu">here</a>
        </p>
        </article>
        
        <article class="ng-scope">
        <h2>Get Connected</h2>
        <p>
            Slack: Use your @byu.edu email to create an account on <a href="https://byucompsci.slack.com" target="_blank">byucompsci.slack.com</a>
        </p>
        <p>
            Discord: <a href="https://discord.gg/X5BjgGK" target="_blank">BYU CS Discord Server</a>
        </p>
        <p>
            Instagram: <a href="https://www.instagram.com/byu_acm/?hl=en" target="_blank">byu_acm</a>
        </p>
        <p>
            Twitter: <a href="https://twitter.com/byuacm?lang=en" target="_blank">BYU ACM</a>
        </p>
        <p>
            Facebook: <a href="https://www.facebook.com/acmbyu/" target="_blank">BYU ACM</a>
        </p>
        </article>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    data() {
        return {
            networking_officer: "Carson Campbell",
        }
    },
    methods: {
        load: function() {
            axios.post('/acm/about').then( res => {
                this.networking_officer = res.data.networking_officer;
            });
        }
    },
    created: function() {
        this.load();
    }

}
</script>

<style scoped>

.about-container {
  max-width: 1000px;
  margin: 0 auto;

}
</style>
