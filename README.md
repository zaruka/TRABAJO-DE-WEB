TRABAJO-DE-WEB
==============

desarrolle los siguientes ejercicios utilizando java script y html5

<!DOCTYPE html>
<html style="background-color:#DFE9FF;">

	<head>
		<center>
	<h3>Invertir la cadena de texto</h3>
	</head>

	<body>
	<input type="text" name="caja" id="caja">
	<br></br>
	<input type="button" value="Invertir Cadena" onClick="invertir(caja.value)" >

	</body>

</html>


<script type="text/javascript">

function invertir(x)
{
var y = " ";


for(i=x.length ; i>=0; i--)
{
   y = y + x.charAt(i);
}

alert("La cadena invertida es: " +y);

}

</Script>



<!DOCTYPE html>
<html style="background-color:#DFE9FF;">
	<head>
		<center>
	<h3>Numeros Primos</h3>
	</head>

	<body>
	<p>Ingrese un valor y verifique si este es un numero primo</p></br>
	<input type="text" name="valor" id="valor"><br></br>
	<input type="button" value="Calcular" OnClick="primos()">
	</body>
		</center>

</html>

<script type="text/javascript"> 
function primos()
{
	var x = document.getElementById("valor").value;
	x = parseInt(x);
    var div = 0 ;
    for (var i = 0; i <= x; i++) {
    	if (x%i == 0) 
    	{
    		div++;
    	}
    }
    if (div >= 3 ) 
    {
    	alert("El numero no es primo");
    }
    else
    {
    	alert("El numero es Primo");
    }
}

</script>


<!DOCTYPE html>
<html style="background-color:#DFE9FF;">
	<center> <h3>Validacion y Suma de Números Binarios</h3>
	<p>Este programa validara y sumara los datos en binarios que se ingresen</p>
	
		Valor 1: <input id="valor1" type="text" ="Ingrese valor 1" /><br>
		Valor 2: <input id="valor2" type="text" label="Ingrese valor 2" /><br></br>
		<input type="button" value="Validar y Sumar" onClick="Sumar(valor1.value , valor2.value)">
	</center>
</html>


<script type="text/javascript"> 
var r, re;

function Sumar(a,b){
validar(a);
validar(b);

r = ( parseInt(a) + parseInt(b) );
re = r.toString(2);
alert("Ambos valores son binarios, la suma de los valores es: " + re);

}


function validar(x)
{
	var	Ban = 0;
	var v, w;

	for (var i = 0; i <= x.length; i++) {
		v = x.charAt(i);
		if((v == 0) || (v == 1)) 
		{
			Ban = 1;
		}
		else
		{
			alert("Porfavor solo ingrese numeros binarios");
			location.href="Sumar y Validar Binario.html";
		}
	}
}

</script>



<!DOCTYPE html>
<html style="background-color:#DFE9FF;">
	<head>
		<center>
		<h3>Validacion de cedulas</h3>
	</head>

	<body>
	<input type="text" id="textocedula" ></br>
	<input type="button" value="Validar Cedula" onClick="validarcedula()">
	</body>
		</center>
		
</html>

<script type="text/javascript">
function validarcedula()
{
	var i;
	var cedula;
	var acumulado;
	cedula=document.getElementById('textocedula').value;
	var instancia;
	acumulado=0;
	for (i=1;i<=9;i++)
	{
		if (i%2!=0)
		{
			instancia=cedula.substring(i-1,i)*2;
			if (instancia>9) instancia-=9;
		}
		else instancia=cedula.substring(i-1,i);
		acumulado+=parseInt(instancia);
	}
	while (acumulado>0)
		acumulado-=10;
	if (cedula.substring(9,10)!=(acumulado*-1))
	{
		alert("Cedula no valida!!");
	}
	else
	{
		alert("Cedula Correcta");
	}
}
</script>



<!DOCTYPE html>
<html style="background-color:#DFE9FF;">

	<head> 
	<meta charset='utf-8'>
	<title>Factura</title>
	</head>
	
		<body >
	<br><center><h2>Sistema de Facturación </h2><br>

		<table border="0px">
	
			<tr><td>Indice Cliente</td>
			<td><input type="text" id="idCLi"></td>
			<td><input type="button" onClick="buscarCLiente(idCLi.value)" value="Buscar"></td></tr>	
			<tr><td>Nombre Cliente</td>
			<td><input type="text" id ="NomCliente" ></td></tr>	
			<tr><td>Nº Productos: </td>
			<td><input id="valor" type="text" onChange="validargenerar(this.value)"></td></tr>
			<td>Descuento</td>
					<td><select id='ComboDes'>
						<option value=0 >0%</option>
						<option value=15>15%</option>
						<option value=25>25%</option>
						<option value=50>50%</option>
					</select></td>

			<tr>
			<td> <input type="text" style="visibility:hidden"> </td>
			<td> <input type="text" style="visibility:hidden"> </td>
			<td> <input type="text" style="visibility:hidden"></td>
			<td> <input type="text" style="visibility:hidden"></td>
			<td> <input type="text" style="visibility:hidden"></td>
			</tr>	

			<tr>
				<td><center>Codigo</center></td>
				<td><center>Descripcion</center></td>
				<td><center>Valor unitario</center></td>
				<td><center>Cantidad</center></td>
				<td><center>Subtotal</center></td>
			</tr>
			</table>


			<tr>
			<div id="celdasFactura">
			</div>
			</tr>


			<table border="0px">
			<tr>
				<td></td>
				<td></td>
				<td></td>
				<td><center>Subtotal</center> </td>
				<td> <input type="text" id="cajasubtotal"></td>
			</tr>

			<tr>
				<td></td>
				<td></td>
				<td></td>
				<td><center>Descuento</center> </td>
				<td><input type="text" id="cajades"></td>
			</tr>

			<tr>
				<td></td>
				<td></td>
				<td></td>
				<td><center>Iva 12 %</center></td>
				<td> <input type="text" id="cajaiva"></td>
			</tr>
			<tr>
				<td></td>
				<td></td>
				<td></td>
				<td><center>Valor Total</center></td>
				<td> <input type="text" id="cajatotal"></td>
			</tr>
			</table>
			<br></br>
			<button onClick="totalFactura()">Calcular Factura!!</button>


	</center>
	</body>

	

</html>



<script type="text/javascript">


var arrayClientes = new Array();
arrayClientes[1] ='Gema';
arrayClientes[2] ='Maria';
arrayClientes[3] ='Cevallos';
arrayClientes[4] ='Santander';
arrayClientes[5] ='Jhon';
arrayClientes[6] ='Carlos';
arrayClientes[7] ='Juan';
arrayClientes[8] ='Jose';
arrayClientes[9] ='Alejando';
arrayClientes[10] ='Carrmen';
arrayClientes[11] ='Wendy';
arrayClientes[12] ='Vilma';
arrayClientes[13] ='Freddy';
arrayClientes[14] ='Santana';
arrayClientes[15] ='Rachel';
arrayClientes[16] ='Steban';
arrayClientes[17] ='Ariel';
arrayClientes[18] ='Danes';
arrayClientes[19] ='Alavaro';
arrayClientes[20] ='Dante';



var arPro = new Array();
arPro[1] ='Shampo';
arPro[2] ='Jabon';
arPro[3] ='Zapatos';
arPro[4] ='cartera';
arPro[5] ='Telfono';
arPro[6] ='Cuarderno';
arPro[7] ='Calculadora';
arPro[8] ='Lapiz';
arPro[9] ='Borrador';
arPro[10] ='Lapicero';
arPro[11] ='Peluca';
arPro[12] ='Pulcera';
arPro[13] ='Camisa';
arPro[14] ='Pantalon';
arPro[15] ='Martillo';
arPro[16] ='Caramelos';
arPro[17] ='Chocolates';
arPro[18] ='Pastillas';
arPro[19] ='Remedios';
arPro[20] ='Cepillos';


var arPre = new Array();
arPre[1] = 1.2;
arPre[2] = 2;
arPre[3] = 12;
arPre[4] = 4.8;
arPre[5] = 2.5;
arPre[6] = 6.8;
arPre[7] = 5.1;
arPre[8] = 6;
arPre[9] = 1;
arPre[10] = 1.1;
arPre[11] = 3.2;
arPre[12] = 2.3;
arPre[13] = 5.5;
arPre[14] = 6.8;
arPre[15] = 5.8;
arPre[16] = 5.2;
arPre[17] = 3;
arPre[18] = 12.5;
arPre[19] = 1.8;
arPre[20] = 18;



var dimension=0;
var dimension2 =0;
var celdas, c1, c2, c3, c4;
var acu=0;

function validargenerar(x){

	var y, nu,cj;
	y=x.length;
	
	for (i=0;i<y;i++){
	nu=parseInt(x.charAt(i));
		if((nu=="0") || (nu=="1") || (nu=="2") || (nu=="3") || (nu=="4") || (nu=="5") || (nu=="6") || (nu=="7") || (nu=="8") || (nu=="9"))
		{}else{
		var a=1;
		}
	}

	if(a==1) {
		alert("Por favor solo ingrese numeros");
	}

	cj=parseInt(x);
		for(j=1; j<=x; j++){
			acu = acu+1;
			c1 = "<tr> <td><input type='text' id='ide"+acu+"'> </td><td> <input type='button' value='Buscar' onClick='buscarProducto(ide"+acu+".value, "+acu+")'></td>  <td><input type='text' id='des"+acu+"'> </td>";
			c2 = "<td> <input type='text' id='val"+acu+"' onChange='calcular(val"+acu+".value, cant"+acu+".value, sub"+acu+".id)'></td>";
			c3 = "<td> <input type='text' id='cant"+acu+"' onChange='calcular(val"+acu+".value, cant"+acu+".value, sub"+acu+".id)'></td>";
			c4 = "<td> <input type='text' id='sub"+acu+"' value='0'> </td> </tr><br>";
			celdas = c1+c2+c3+c4;
			document.getElementById("celdasFactura").innerHTML += celdas;
		}
		return acu;
}

function buscarCLiente(idCliente){
	dimension = arrayClientes.length;
	for (i =1; i<=dimension; i++)
	{
		if (arrayClientes[idCliente] != " ")
		{
			document.getElementById('NomCliente').value = arrayClientes[idCliente];
			break;
		}
	}
}


function buscarProducto(iden, lugar){
dimension2 = arPro.length;
	for (i =1; i<=dimension; i++)
	{
		if (arPro[iden] != " ")
		{
			document.getElementById('des'+lugar+'').value = arPro[iden];
			document.getElementById('val'+lugar+'').value = arPre[iden];
			break;
		}
	}


}



function calcular(val, cant, subto) {
	multi = (val * cant); 
	document.getElementById(subto).value = multi;

}

var s, sub=0;
function totalFactura () {
	for( var i=1; i<=acu; i++){
		s = document.getElementById('sub'+i+'').value;
		s = parseFloat(s);
		sub += s;
	}

	document.getElementById("cajasubtotal").value = sub;

	var vcd =	document.getElementById("ComboDes").value;
	var vdes = (sub * vcd)/100;

	document.getElementById("cajades").value = vdes;

 
 	iva = (sub *12)/100;
	document.getElementById("cajaiva").value = iva;

	vtotal = (sub + iva)- vdes ;
	document.getElementById("cajatotal").value = vtotal;

}


</script>

