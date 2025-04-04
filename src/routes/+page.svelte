<script>
    import Comment from "../components/Comment.svelte"
    import Data from "../components/Data.svelte"
    import Visualization from "../components/Visualization.svelte"
    import Variable from "../components/Variable.svelte"
    import Table from "../components/Table.svelte"
    import Chart from "../components/Chart.svelte"
    let data = [];
  
    async function fetchData() {
      try {
        const response = await fetch('http://localhost:8000/');
        data = await response.json();
        console.log(data)
      } catch (error) {
        console.error('Error fetching data:', error);
      }
    }
    fetchData()
  </script>
<main>
    <div class="container">
        <div class="code">
            <Variable id={"prompt"} type={"Prompt"} content={"For each team, show the goals in the finals compared to over all stages using a bar chart"} />
            {#if data}
                {#each data as step, i}
                    {#if Object.keys(step['Comment']).length != 0 }
                    <Comment line={i} step={step['Comment']}/>
                    {:else if Object.keys(step['Data']).length != 0}
                    <Data line={i} step={step['Data']}/>
                    {:else if Object.keys(step['Visualization']).length != 0}
                    <Visualization line={i} step={step['Visualization']}/>
                    {/if}
                {/each}
            {/if}
        </div>
        <div class="sidebar">
            <Table />
            <Chart />
        </div>
    </div>
</main>
<style>
    main {
        font-family: Helvetica, Arial, sans-serif;
        text-align: left;
        color: #14525C;
    }
    .container {
        display: flex;
        flex-direction: row;
        justify-items: center;
    }

    .code {
        width: 60%;
        padding: 1em;
    }

    .sidebar {
        width: 40%;
        padding: 1em;
    }
</style>
