<script>
	import firebase from 'firebase/app';
	import {onMount} from 'svelte';
  import { goto,stores } from '@sapper/app';
  export let segment;

  const {session} = stores()


	onMount( async()=>{
		 fetch('https://api.coingecko.com/api/v3/simple/price?ids=bitcoin&vs_currencies=usd')
		.then(res=>res.json())
		.then(data => console.log(data));
		
	})

</script>

<div id = "content"> 
 	<div class="page-container">
    	<div class="center">
    		<div class="header">CryptoCurrency</div>
			   <h1><a href="login">Login</a></h1>
    	</div>
	</div>
</div>

<style>
  /* Container to center page on a screen */
  .center { grid-area: middle; }
  .page-container{
      grid-template-areas: 'left middle right';
      padding: 10px;
      align-content: center;
      justify-content: center;
      max-width: 80%;
      margin-left: auto;
      margin-right: auto;
  }

  .page-container > div {
    text-align: center;
    padding: 5px 0;
    align-items: center;
  }

  /* Mobile phone constraints */
  @media only screen and (max-width: 670px) {
    .page-container {
      grid-template-areas: 'left middle right';
      padding: 10px;
      align-content: center;
      justify-content: center;
      max-width: 95%;
      margin-left: auto;
      margin-right: auto;
    }
  }
  /* General */
  #content {
  	border-bottom: 1px solid rgba(255,62,0,0.1);
	font-weight: 300;
	padding: 0 1em;
    text-align: center;
    margin-left: auto;
    margin-right: auto;
    font-size: 14pt;
    min-height: 110%;
    background-color: hsl(0, 0%, 98%);
    z-index: -1;
  }

  .header {
    font-size: 40px;
    color: hsl(210, 35%, 30%);
  }

  a {
    display: block;
    color: hsl(210, 35%, 70%);
    text-align: center;
    padding: 15px 15px;
    text-decoration: none;
    font-size: 18px;
  }

  a:hover {
    color: hsl(210, 35%, 40%);
  }

</style>

