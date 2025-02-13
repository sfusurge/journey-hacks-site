<script lang="ts">
  import StickyLabel from "../StickyLabel.svelte";
  import Accordion from "../Accordion.svelte";

  type FAQ = {
    question: string;
    answer: string;
  };

  let FaqObjects: FAQ[] = [
    {
      question: "What is JourneyHacks?",
      answer:
        "JourneyHacks is a 12 hour hackathon where beginners are encouraged to utilize skills learnt in our JourneyHacks workshops as well as existing skills to create a project. Teams and individual participants are encouraged to collaborate, create meaningful impact, and challenge other teams.",
    },
    {
      question: "What should I bring?",
      answer:
        "You should bring your laptop, charger, and any other tech essentials you need for coding and designing. Unlike StormHacks, we will not be providing hardware so please bring those materials if you wish to work on a hardware project! Don't forget to carry your ID for registration purposes. It's also a good idea to have a water bottle to stay hydrated and a notebook for jotting down ideas.",
    },
    {
      question: "I don’t code, can I still participate?",
      answer:
        "Great projects are more than just coding. We welcome all kinds of programmers, entrepreneurs, designers and everyone. If you run into any problems or questions, mentors are always there to help. Keep in mind, by the time you walk out, you will have a recipe book of new skills. Our JourneyHacks workshops are also available to build your technical background.",
    },
    {
      question: "How much experience do I need to participate at JourneyHacks?",
      answer:
        "JourneyHacks is a beginner focused hackathon for first and second year students or those wanting to just try what a hackathon is all about! It's the perfect place to start your tech journey. We'll have mentors and workshops to guide you, so come eager to learn, and you'll leave with new skills and knowledge.",
    },
    {
      question: "Where and when will JourneyHacks be?",
      answer:
        "JourneyHacks will take place at SFU Burnaby in the Applied Science Building (ASB) from 9am to 9pm. The sign in desk, opening presentation, and workshops will also take place here. Participants are free to spread out around campus while they work on their projects.",
    },
    {
      question: "What can I do if I don’t have a team?",
      answer:
        "No worries at all! JourneyHacks is a fantastic place to meet new people and form teams. We'll have a team formation session after the opening presentation, so stay after to mingle and find your perfect match of skills and interests. Alternatively, we will also have a team formation channel on our Discord.",
    },
    {
      question: "How many people can I have in a team?",
      answer:
        "We ask you have no more than 4 people in a team. It's the ideal size to ensure everyone can contribute significantly and collaborate effectively.",
    },
    {
      question: "Do I need to stay for the entire event?",
      answer:
        "We understand that students have classes and other commitments, so JourneyHacks is designed to be flexible. We welcome you to drop in and out as needed, making it easy to tailor your experience to the workshops, mentorship, and activities that interest you most.",
    },
    {
      question: "Can I work on a previous project?",
      answer:
        "To ensure a level playing field and to foster new ideas, we ask that you start fresh and not work on pre-existing projects during JourneyHacks.",
    },
    {
      question: "Can non-SFU students participate?",
      answer:
        "Unfortunately, JourneyHacks is only for SFU students. However, we encourage non-SFU students to apply for StormHacks in the fall!",
    },
    {
      question: "Is there a theme to the hackathon?",
      answer:
        'Yes, our theme this year is "cooking," which we hope will inspire hackers to not be afraid to push themselves to incorporate new skills and technology into their projects similar to how cooking can be very experimental. Coding and cooking are both require a lot of trial and error so we encourage you to cook up a storm, just like Stormy and Sparky! Also to clarify, your project doesn’t need to be cooking based or related to the theme. ',
    },
    {
      question: "Will food be provided?",
      answer:
        "Yes, lunch and dinner will be provided with drinks to all hackers.",
    },
    {
      question: "What kind of activities will there be?",
      answer:
        "We will have some side events throughout the hackathon to give hackers a break from coding and brain storming, there will be chances to complete challenges and win prizes throughout the day and exciting workshops will be available!",
    },
  ];
</script>

<div id="faq">
  <div
    style="display: flex; flex-direction:column; gap:1rem; width:fit-content; margin-left:auto; margin-right:auto;"
  >
    <StickyLabel>FAQ</StickyLabel>

    <div class="max-w-[960px] mx-auto grid md:grid-cols-2 gap-3 md:gap-8">
      <div class="flex flex-col gap-3">
        {#each FaqObjects.slice(0, Math.ceil(FaqObjects.length / 2)) as faq}
          <Accordion question={faq.question} answer={faq.answer}></Accordion>
        {/each}
      </div>

      <div class="flex flex-col gap-3">
        {#each FaqObjects.slice(Math.ceil(FaqObjects.length / 2)) as faq}
          <Accordion question={faq.question} answer={faq.answer}></Accordion>
        {/each}
        <Accordion
          question="How can I learn more about your hackathons?"
          answer="We are always available for questions about our hackathons on our "
          link="https://discord.gg/Rg4mwHvKjd"
          linkText="Discord"
        ></Accordion>
      </div>
    </div>
  </div>
</div>

<style>
  #faq {
    padding: 2rem;
    background-color: #dfb19b;
  }
</style>
