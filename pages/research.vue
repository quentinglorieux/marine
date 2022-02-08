<template>
<div> 
  <div v-for="item in items" v-bind:key="item">
    <ResearchItem
    v-bind:science_object="item" >
    </ResearchItem>  </div>

  <!-- <div v-for="item in items" v-bind:key="item">
      <ResearchItem
      v-bind:title="item.title" 
      v-bind:content="item.content" 
      v-bind:image_name="item.image_name" >
      </ResearchItem>  
  </div> -->

</div>
</template>

<script>
export default {
  name: 'ResearchPage',
   data() {
  return {
    items: [
      { title: 'Plasticity of the Sense of Agency' ,
        content: `How do we entertain the strong feeling that we are the owners of our own actions? 
                The sense of agency (SoA) is the feeling that we are at the origin of our own volitional actions.
                It is central to the fluency of action, responsibility and wellbeing in humans.
                It can be degraded in the modern world when healthy humans interact with more and more sophisticated 
                technologies or in neuropsychiatric patients suffering from depression or schizophrenia.
                Uncovering the plasticity of the SoA is thus crucial for helping humans to regain the ownership 
                of their actions, optimize their choices and improve their mental health. In our lab, we are currently 
                1) creating a brain computer interface (BCI) that disturbs the SoA, 
                2) characterizing how the disturbed SoA can recover through spontaneous mechanisms of plasticity and 
                3) designing laboratory and everyday life interventions that accelerate the plasticity of the SoA. 
                This will help us to understand how the SoA is instantiated, maintained, and possibly dynamically modified.`,
        image_name: 'Sans-titre-3.png'
        }, 
        { title: 'Neural substrates of Spontaneous Thoughts' ,
        content: `When awake, most of us believe we are experiencing a stream of consciousness, which would be made of external or internal images, sounds and other sensations, or words (e.g., when talking to ourselves). To explore such conscious experience, many neuroscience studies have focused on characterizing the neural substrate of the content of consciousness (being conscious of a face vs. of a house). Other studies have characterized various states of consciousness (awake, asleep with or without dreaming, anesthesia, disorders of consciousness…) Our research aims to bridge the gap between content and state studies of consciousness. For this, we are exploring the neural correlates not only of the content, but also of the vividness and quality of spontaneous thoughts in humans..`,
        image_name: 'Sans-titre-5.png'
        }, 
        { title: 'Conscious Perception' ,
        content: `Our recent research focused on characterizing the neural substrate of conscious visual perception. Through a series of studies, we characterized the mechanisms linking brain oscillations, the fronto-parietal networks, visuospatial attention, objective visual performance (such as discrimination accuracy) and finally subjective perception, also named visual awareness.`,
        image_name: 'Sans-titre2.png'
       }, 
      ]
  }
}
}
</script>
