<script>
  const plans = [
    {
      title: "Basic",
      montlhy: "19.99",
      annually: "199.99",
      perks: ["500 GB Storage", "2 Users Allowed", "Send up to 3 GB"],
    },
    {
      title: "Professional",
      montlhy: "24.99",
      annually: "249.99",
      perks: ["1 TB Storage", "5 Users Allowed", "Send up to 10 GB"],
      featured: true,
    },
    {
      title: "Master",
      montlhy: "39.99",
      annually: "399.99",
      perks: ["2 TB Storage", "10 Users Allowed", "Send up to 20 GB"],
    },
  ];
</script>

<main>
  <h1>Our Pricing</h1>
  <div class="plans">
    {#each plans as plan}
      <div class={`plan ${plan.featured ? "featured" : ""}`}>
        <h2>{plan.title}</h2>
        <p class="price">$ {plan.montlhy}</p>
        <div>
          {#each plan.perks as perk}
            <div class="perk">
              <p>{perk}</p>
            </div>
          {/each}
        </div>
        <button>Learn More</button>
      </div>
    {/each}
  </div>
</main>

<style>
  main {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  h1 {
    text-align: center;
    color: var(--grayish-blue);
    margin: 0;
    margin-bottom: 2rem;
  }
  .plans {
    display: grid;
    grid-template-columns: 1fr;
  }

  .plan {
    padding: 2rem;
    text-align: center;
    background: white;
    box-shadow: 0 0 1rem var(--light-grayish-blue);
    border-radius: 1rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .plan.featured {
    background: linear-gradient(
      to bottom,
      hsl(236, 72%, 79%),
      hsl(237, 63%, 64%)
    );
    color: white;
    height: 98%;
    align-self: center;
  }

  .featured button {
    background: white;
    color: var(--grayish-blue);
  }

  .featured button:hover {
    color: var(--very-light-grayish-blue);
    outline-color: var(--very-light-grayish-blue);
  }

  h2 {
    margin: 0;
  }
  .price {
    font-size: 5rem;
    margin-block: 1rem;
  }

  .perks {
    margin-bottom: 2rem;
  }

  .perk {
    padding-block: 0.5rem;
    border-bottom: 1px solid var(--very-light-grayish-blue);
  }

  button {
    border: none;
    width: 100%;
    cursor: pointer;
    padding: 1rem;
    text-transform: uppercase;
    font-size: 0.9rem;
    font-weight: bold;
    border-radius: 0.5rem;
    transition: 0.2s all ease;
    color: white;
    background: linear-gradient(
      to right,
      hsl(236, 72%, 79%),
      hsl(237, 63%, 64%)
    );
  }

  button:hover {
    color: hsl(237, 63%, 64%);
    background: transparent;
    outline-width: 1px;
    outline-style: solid;
    outline-color: var(--dark-grayish-blue);
  }

  @media (min-width: 768px) {
    .plans {
      grid-template-columns: 1fr 1fr 1fr;
    }
  }
</style>
