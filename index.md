<p align="justify">
In this post, we show the demo of the singing voice synthesis method of Stripe U-net
</p>

### Overview
<p align="justify">
Singing voice synthesis is a generative task that not only involves multi-dimensional control of the singing model, including lyrics, pitch, and duration, but also includes the timbre of the singer's singing and singing skills such as vibrato. Singing voice has rich expression, accurate and powerful modeling technology is necessary. In the proposed method, the task of synthesizing singing voice is treated as the translation task between lyrics and music score and spectrum. The lyrics and music score information are encoded into a two-dimensional feature representation through the convolutional layer in prenet, and the two-dimensional feature and its own frequency spectrum are mapped to the target spectrum in an autoregressive manner through the U-net network. In addition, the composition relationship of the fundamental frequency domain harmonics in the singing voice presents a striped structure in the frequency spectrum, and the stripe pooling method is used to replace the alternate segment pooling method to better learn the vertical frequency relationship in the frequency spectrum and the cross fundamental frequency harmony characteristics of changes in the time domain. The experimental results on the public dataset Kiritan show that the proposed method can synthesize more natural singing voices.
</p>

![Model Architecture ](assets/imgae/fig1.png)
<p align="center">Figure.1 Overview of the proposed singing voice synthesis system.</p>

### Stripe pooling module

![Spectrograms](assets/imgae/fig2.png)
<p align="center">Figure.2 Stripe pooling of the spectrum.</p>

### Results

<script>
function pauseOthers(ele) {
    $("audio").not(ele).each(function (index, audio) {audio.pause();});
}
</script>

<style>
.main-content table {
    display: inline-table;
}
table {
    table-layout:fixed;
    width: 100%;
    overflow: hidden;
}
#player{
    width: 100%;
}
</style>

<table>
    <tr>
        <th> Song </th>
        <th> Ground Truth</th>
        <th> Generated </th>
    </tr>
    <tr>
        <th> 1 </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/raw/46_48_110.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/synthesis/latest_G_46_48_110.mp3" type="audio/mpeg"></audio> </th>
    </tr>
    <tr>
        <th> 2</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/raw/47_14_92.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/synthesis/latest_G_47_14_92.mp3" type="audio/mpeg"></audio> </th>
    </tr>
    
      <tr>
        <th> 3 </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/raw/48_15_98.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/synthesis/latest_G_48_15_98.mp3" type="audio/mpeg"></audio> </th>
    </tr>
    
    
      <tr>
        <th> 4 </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/raw/49_17_75.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/synthesis/latest_G_49_17_75.mp3" type="audio/mpeg"></audio> </th>
    </tr>
    
    
    
      <tr>
        <th> 5 </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/raw/50_28_97.mp3" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/synthesis/latest_G_50_28_97.mp3" type="audio/mpeg"></audio> </th>
    </tr>

</table>