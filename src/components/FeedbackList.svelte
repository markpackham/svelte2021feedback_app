<script>
import {FeedbackStore} from '../stores'
import {fade, scale} from 'svelte/transition'
import FeedbackItem  from './FeedbackItem.svelte'

// import {onMount, onDestory} from "svelte"
// let feedback = []

// const unsubscribe = FeedbackStore.subscribe((data)=> feedback = data)

// onMount(()=>{
//     console.log("I'm just like in React, I show up when component is mounted")
// })

// onDestory(()=>{
//     unsubscribe()
// })
</script>

{#each $FeedbackStore as fb (fb.id)}
<div in:scale out:fade="{{duration: 500}}">
    <FeedbackItem item={fb} on:delete-feedback />
</div>
{/each}