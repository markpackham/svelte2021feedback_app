<script>
  import {FeedbackStore} from '../stores'
  // export let count
  // export let average

// $: count = feedback.length
// $: average = feedback.reduce((a, {rating})=> a + rating,0) / count
$: count = $FeedbackStore.length
$: average = $FeedbackStore.reduce((a, {rating})=> a + rating,0) / count
</script>

<div class="feedback-stats">
  <h4>{count} Reviews</h4>
  <h4>Ratings Average: {average}</h4>
</div>

<style>
    .feedback-stats {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
 </style>