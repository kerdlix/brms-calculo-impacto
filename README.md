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

