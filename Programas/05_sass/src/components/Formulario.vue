<script>

</script>

<template>
  <div>
    <h2>Formulario</h2>
    <form>
      <div>
        <label>Moneda Nacional:</label>
        <select required>
          <option value="" disabled selected>Seleccione una moneda</option>
          <option>MXN</option>
          <option>USD</option>
          <option>EUR</option>
        </select>
      </div>

      <div>
        <label>Criptomoneda:</label>
        <select required>
          <option value="" disabled selected>Seleccione una criptomoneda</option>
          <option>BTC</option>
          <option>ETH</option>
          <option>LTC</option>
        </select>
      </div>

      <div>
        <button type="submit">Cotizar</button>
      </div>

    </form>
  </div>

</template>