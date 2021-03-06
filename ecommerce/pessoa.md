nome | RG | CPF | Telefone | Endereço | 

```json
id: int,
nome/razaoSocial: string(>=2),
apelido/fantasia: string(>=2),
```
<details>
  <summary><pre>
telefones: ?[
{
  ativo: bool,
  codigoOperadora: int?(algarismos: 2),
  prefixoInternacional(DDI): int?(algarismos: 1:3),
  prefixoNacional(codigoArea, DDD): int?(algarismos: 2),
  numero(SN - Subscriber Number): int(algarismos: 6:9)
}],</pre></summary>

  <pre>
Implementação:
  1ª Opção: cada chave-valor do Javascript Object pode corresponder a um input
  2ª Opção: um único input para cada telefone, o valor é dividido em substrings cujos valores são alocados às chaves
  correspondentes através de uma função
    pattern input: 

Links: https://www.cm.com/blog/how-to-format-international-telephone-numbers/
  </pre>
</details>

```json
enderecos: ?[
{
  ativo: bool,
```
<details>
  <summary><pre>
  CEPbrasileiro: string() | int(8),</pre></summary>

  https://www.mbi.com.br/mbi/biblioteca/paises/codigo-postal/
</details>

```json
  país: {
    codigoISO2: string(2, [A-Z]),
    codigoISO3: string(3, [A-Z]),
    nome: string
  }
  UF: {
    idIBGE: int(11:17 || 21:29 || 31:33 || 35 || 41:43 || 50:53),
    sigla: string(2, [A-GI-JL-PR-T]),
    nome: string
  },
  municipio: {
    idIBGE: int(algarismos: 5),
    nome: string
  }
  bairro/distrito: string,
  logradouro: {
    tipo: string,
    nome: string
  },
  numero: int,
  quadra: int,
  lote: int,
  complemento: string
}],
```
