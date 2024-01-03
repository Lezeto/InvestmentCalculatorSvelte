<script>
  let m = 0;
  let i = 0;
  let t = 0;
  let result = 0;

  function calculate() {
    // Reajustar i e t según las especificaciones
    const adjustedI = Math.pow(1 + i / 100, 1 / 12);
    const adjustedT = t * 12;

    // Calcular el resultado
    result = Math.round(m * ((1 - Math.pow(adjustedI, adjustedT)) / (1 - adjustedI)));
  }
</script>

<style>
  /* Estilos opcionales aquí */
</style>

<main>
  <h1>Calculadora Rentabilidad de Ahorro Mensual</h1>

  <label>
    Ahorro Mensual (m):
    <input bind:value={m} type="number" />
  </label>

  <label>
    Tasa de interés anual (i %):
    <input bind:value={i} type="number" />
  </label>

  <label>
    Período en años (t):
    <input bind:value={t} type="number" />
  </label>

  <button on:click={calculate}>Calcular</button>

  {#if result !== 0}
    <p>El resultado es: {result}</p>
  {/if}
</main>
