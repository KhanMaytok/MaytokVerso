---
layout: page
title: Dona
permalink: /dona/
---


<button id="colabora"> Colaborar con mi pobreza</button>

Tarjetas de prueba:

<table>
	<thead>
		<tr>
			<th class="first">Marca</th>
			<th class="first">Número</th>
			<th class="first">Mes/Año</th>
			<th class="first">CVV</th>
			<th class="first">Descripción</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><span>Visa</span></td>
			<td><span class="table-params">4111 1111 1111 1111</span></td>
			<td>09/2025</td>
			<td>123</td>
			<td>Venta exitosa</td>
		</tr>
		<tr>
			<td><span>Master Card</span></td>
			<td><span class="table-params">5111 1111 1111 1118</span></td>
			<td>06/2025</td>
			<td>039</td>
			<td>Venta exitosa</td>
		</tr>
		<tr>
			<td><span>American Express</span></td>
			<td><span class="table-params">3712 1212 1212 122</span></td>
			<td>11/2025</td>
			<td>2841</td>
			<td>Venta exitosa</td>
		</tr>
		<tr>
			<td><span>Diners Club</span></td>
			<td><span class="table-params">360012 1212 1210</span></td>
			<td>04/2025</td>
			<td>964</td>
			<td>Venta exitosa</td>
		</tr>
	</tbody>
</table>

<!-- Incluye Culqi Checkout en tu sitio web-->
<script src="https://checkout.culqi.com/js/v3"></script>

<script>
	// Configura tu llave pública
	Culqi.publicKey = 'pk_test_rM6KZiN3i3esQITU';
	// Configura tu Culqi Checkout
	Culqi.settings({
		title: 'Universo Maytok',
		currency: 'PEN',
		description: 'Donación fantástica',
		amount: 500
	});
	// Usa la funcion Culqi.open() en el evento que desees
	
	document.getElementById('colabora').addEventListener('click', function(e) { 
		// Abre el formulario con las opciones de Culqi.settings
		Culqi.open();
		e.preventDefault();
	}, false);

	function culqi() {
		if (Culqi.token) { // ¡Objeto Token creado exitosamente!
			var token = Culqi.token.id;
			//fetch(`http://127.0.0.1:8000/payments/create/?token=${token}`)
			//En esta linea de codigo debemos enviar el "Culqi.token.id"
			//hacia tu servidor con Ajax
		} else { // ¡Hubo algún problema!
			// Mostramos JSON de objeto error en consola
			console.log(Culqi.error);
			alert(Culqi.error.user_message);
		}
	}
</script>
