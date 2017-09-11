# BRMS Cálculo de Impacto

## Variáveis de entrada para cada regra
* Score Origem
* Score Destino
* Segmento Destino
* Rating Destino
* Setor Origem
* Pagamento
* Recebimentos (Lista)

## Execução dos Testes

### URL Post
http://localhost:8080/kie-server/services/rest/server/containers/instances/impacto

### Teste 1
```
<batch-execution lookup="mySession">
<insert out-identifier="c1">
	<com.redhat.impacto.Calculo>
		<scoreOrigem>4.0</scoreOrigem>
		<scoreDestino>1.0</scoreDestino>
		<segmentoDestino>GRANDES_EMPRESAS</segmentoDestino>
		<ratingDestino>BOM</ratingDestino>
		<setorOrigem>SETOR_PETROLEO</setorOrigem>
		<pagamento>6</pagamento>
		<recebimentos>
			<com.redhat.impacto.Recebimento>
				<origem>A</origem>
				<recebimento>1</recebimento>
			</com.redhat.impacto.Recebimento>
			<com.redhat.impacto.Recebimento>
				<origem>B</origem>
				<recebimento>3</recebimento>
			</com.redhat.impacto.Recebimento>
			<com.redhat.impacto.Recebimento>
				<origem>C</origem>
				<recebimento>6</recebimento>
			</com.redhat.impacto.Recebimento>
		</recebimentos>		
	</com.redhat.impacto.Calculo>
</insert>
<start-process processId="impacto.Fluxo">
</start-process>
<fire-all-rules />
</batch-execution>
```

### Teste 2
```
<batch-execution lookup="mySession">
<insert out-identifier="c2">
	<com.redhat.impacto.Calculo>
		<scoreOrigem>4.0</scoreOrigem>
		<scoreDestino>7.0</scoreDestino>
		<segmentoDestino>PEQUENAS_EMPRESAS</segmentoDestino>
		<ratingDestino>RUIM</ratingDestino>
		<setorOrigem>SETOR_ENERGIA</setorOrigem>
		<pagamento>12</pagamento>
		<recebimentos>
			<com.redhat.impacto.Recebimento>
				<origem>A</origem>
				<recebimento>1</recebimento>
			</com.redhat.impacto.Recebimento>
			<com.redhat.impacto.Recebimento>
				<origem>B</origem>
				<recebimento>12</recebimento>
			</com.redhat.impacto.Recebimento>
			<com.redhat.impacto.Recebimento>
				<origem>C</origem>
				<recebimento>1</recebimento>
			</com.redhat.impacto.Recebimento>
			<com.redhat.impacto.Recebimento>
				<origem>D</origem>
				<recebimento>1</recebimento>
			</com.redhat.impacto.Recebimento>
		</recebimentos>		
	</com.redhat.impacto.Calculo>
</insert>
<start-process processId="impacto.Fluxo">
</start-process>
<fire-all-rules />
</batch-execution>
```

## Construção

### Organizational Units
<p align="center"><img src="/images/00.png?raw=true"></p>

### Project
<p align="center"><img src="/images/01.png?raw=true"></p>
<p align="center"><img src="/images/02.png?raw=true"></p>

### Data Object
<p align="center"><img src="/images/03.png?raw=true"></p>
<p align="center"><img src="/images/04.png?raw=true"></p>
<p align="center"><img src="/images/05.png?raw=true"></p>
<p align="center"><img src="/images/06.png?raw=true"></p>
<p align="center"><img src="/images/07.png?raw=true"></p>

### Ruleflow
<p align="center"><img src="/images/18.png?raw=true"></p>

### Grupo totalReceb
<p align="center"><img src="/images/08.png?raw=true"></p>

### Grupo pesoRelac
<p align="center"><img src="/images/16.png?raw=true"></p>

### Grupo impacto
<p align="center"><img src="/images/15.png?raw=true"></p>

### Grupo fatorAbsorcao
<p align="center"><img src="/images/09.png?raw=true"></p>

### Grupo tabelas
<p align="center"><img src="/images/11.png?raw=true"></p>
<p align="center"><img src="/images/12.png?raw=true"></p>
<p align="center"><img src="/images/13.png?raw=true"></p>

### Grupo origensNeutras
<p align="center"><img src="/images/10.png?raw=true"></p>

### Grupo fatorImpacto
<p align="center"><img src="/images/14.png?raw=true"></p>

### Grupo scoreFinal
<p align="center"><img src="/images/17.png?raw=true"></p>

### Decision Server
<p align="center"><img src="/images/19.png?raw=true"></p>

### Cenários de testes
<p align="center"><img src="/images/20.png?raw=true"></p>
<p align="center"><img src="/images/21.png?raw=true"></p>

