<template>
    <div class="lecture">
      <div id="allLesson">
          <h4>Escuchar toda la lección.</h4>
          <div>
            <audio controls >
                <source src="audio/full-text.mp3" type="audio/mpeg">
            </audio>           
          </div>          
      </div>        
      <div>
          <h1>
              Topic: Volcanic eruptions.
          </h1>
            <audio controls >
                <source src="audio/1.mp3" type="audio/mpeg">
            </audio>         
          <h2>
              The Popocatepetl.
          </h2>       
      </div>
      <div >
          <div>
              <h3>Intro.</h3>
                <audio controls >
                    <source src="audio/2.mp3" type="audio/mpeg">
                </audio>                
                <p>Hi to everyone!</p>
                <p>I’m Sergio Emiliano.</p>
                <p>This presentation is about Popocatepetl volcano</p>
          </div>

          <div>
              <h3>Why did I choose the topic?</h3>
               <audio controls >
                    <source src="audio/3.mp3" type="audio/mpeg">
                </audio>              
              <p>
                  I’ve chosen this topic because the city where we live is surrounded by three volcanoes and one of them the Popocatepetl is considered very dangerous. Furthermore it is currently active.                
              </p>
          </div>

          <div>
              <h3>Why is it important to know that information?</h3>
               <audio controls >
                    <source src="audio/4.mp3" type="audio/mpeg">
                </audio>              
              <p>
                  This information is important because it helps us to know the risk of living near an active volcano. Also, It allows us to be ready in case an emergency may happen.
              </p>
          </div>
          <div>
              <h3>Volcano Features</h3>
               <audio controls >
                    <source src="audio/5.mp3" type="audio/mpeg">
                </audio>              
              <p>
                  <ul>
                      <li>Its name comes from the Nahuatl dialect. It means Smoking Mountain.</li>
                      <li>It is approximately 730,000 years old. </li>
                      <li>It has a conic shape.</li>
                      <li>It is in the states of Puebla, Morelos, and Mexico, in central Mexico. </li>
                      <li>Puebla city is the closest to the volcano. It is 43 kilometers away.</li>
                      <li>It is the second-highest peak in Mexico. The summit is at about 5.4 kilometers elevation.
                      </li>
                      <li>Its crater has a diameter of 850 m. at its widest part.</li>
                  </ul>
              </p>
          </div>
          <div>
              <h3>The risks of living near the volcano are.</h3>
               <audio controls >
                    <source src="audio/6.mp3" type="audio/mpeg">
                </audio>              
              <p>
                  In 1991 an increase in their activity began, and the fumaroles were already clearly visible from distances of around 50 kilometers.
              </p>
              <p>
                  It is very difficult to know in advance which areas would be affected in the event of an eruption. The direction of the winds plays an important role in the ash and gas dispersal.
              </p>
              <p>
                  There are many communities settled near the crater. So, its inhabitants are in danger.
              </p>
          </div>
          <div>
              <h3>Volcano Monitoring</h3>
               <audio controls >
                    <source src="audio/7.mp3" type="audio/mpeg">
                </audio>              
              <p>
                  The government organism in charge of volcano monitoring is named CENAPRED. It uses a color semaphore to classify the volcano danger.
              </p>
              <p>
                  The red color is considered an imminent eruption.
              </p>
          </div>
          <div>
              <h3>Risks map</h3>
               <audio controls >
                    <source src="audio/8.mp3" type="audio/mpeg">
                </audio>              
              <p>
                  Researchers from the National Autonomous University of Mexico (UNAM) designed a risk map that documents the affected areas with lava, pyroclastic flows, ash, and mud streams.
              </p>
              <p>
                  There are three risk zones: red, orange, and yellow. There are plans to evacuate the nearest communities (those in the red zone).
              </p>
              <p>
                  The city of Puebla is in the yellow zone. So, a moderate eruption would be impacted only by the ashfall.
              </p>
          </div> 
          <div>
              <h3>Preventive Measures</h3>
               <audio controls >
                    <source src="audio/9.mp3" type="audio/mpeg">
                </audio>              
              <p>
                  <ul>
                      <li>Be attentive to the notices of the authorities in case of any emergency.</li>
                      <li>Stay away from the crater.</li>
                      <li>Keep the evacuation routes in good condition and with the indicated signs.</li>
                      <li>Verify that temporary shelters have adequate conditions for their function.</li>
                      <li>Conduct drills.</li>
                      <li>Review procedures and resources in case of a possible evacuation.</li>
                  </ul>
              </p>
          </div>                                        
          <div>
              <h3>In Summary</h3>
               <audio controls >
                    <source src="audio/10.mp3" type="audio/mpeg">
                </audio>              
                <h4>
                    Knowing about the Popocatepetl helps us prevent a catastrophe in the event of an eruption.
                </h4>
                <p>
                    Thank you for your attention.
                    <br>
                    I hope you have enjoyed this presentation.
                    <br>
                    If you have any comments, please reach me out to my email.
                </p>              
          </div>
      </div>    
    </div>
</template>

<script>
import { ref } from 'vue';

export default {
    

    name: 'SpeakText',
    setup() {

        const audio = ref(new Audio());
        const currentAudio = ref("");



        const speak = (audioFile) => {
            if (currentAudio.value != audioFile) {
                currentAudio.value = audioFile;
                audio.value = new Audio(audioFile);
            }

            console.log('paused:2:? ', audio.value.paused);
            console.log('Trying to play!', currentAudio.value);
            
            
            if (audio.value.paused) {
                audio.value.play().then(() => { 
                    console.log('playing');
                }).catch((error) => {
                    console.log(error);
                });
            } else {
                audio.value.currentTime = 0;
                audio.value.pause();
            }            
        };

        return { audio, speak };
    }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div.lecture {
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    text-align: left;
    padding: 1em;
    font-size: 1.5em;
    
}

div#allLesson {
    background-color: #a1a1a1;
    padding: 10px;
}
</style>
