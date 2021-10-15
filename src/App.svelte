<script>
import FeedbackForm from './components/FeedbackForm.svelte'
import FeedbackList from './components/FeedbackList.svelte'
import FeedbackStats from './components/FeedbackStats.svelte'
export let feedback = [{}]

$: count = feedback.length
$: average = feedback.reduce((a, {rating})=> a + rating,0) / count

const addFeedback = (e) =>{
  const newFeedback = e.detail
  feedback = [newFeedback, ...feedback]
}

const deleteFeedback = (e) =>{
    const itemId = e.detail
    feedback = feedback.filter((item) => item.id != itemId)
}
</script>

<main class="container">
<FeedbackForm on:add-feedback={addFeedback} />
<FeedbackStats {count} {average} />
<FeedbackList {feedback} on:delete-feedback={deleteFeedback}/>
</main>