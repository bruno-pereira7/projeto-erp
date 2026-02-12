# ERP

## Diagrama UML
```bash
@startuml
package "ERP Core" {
  component CadastroClientes
  component CadastroFornecedores
  component CadastroProdutos
  component RegrasDeNegocio
}

package "CRM" {
  component Leads
  component Oportunidades
}

package "Pedidos" {
  component PedidoVenda
  component PedidoCompra
  component Faturamento
}

package "WMS" {
  component Estoque
  component MovimentacaoEstoque
  component SeparacaoExpedicao
}

package "Financeiro" {
  component ContasReceber
  component ContasPagar
  component FluxoCaixa
  component DRE
}

' Relações com Core
CRM --> CadastroClientes
Pedidos --> CadastroClientes
Pedidos --> CadastroFornecedores
Pedidos --> CadastroProdutos
WMS --> CadastroProdutos
Financeiro --> CadastroClientes
Financeiro --> CadastroFornecedores

' Fluxos principais
Leads --> Oportunidades
Oportunidades --> PedidoVenda

PedidoVenda --> MovimentacaoEstoque
PedidoCompra --> MovimentacaoEstoque

PedidoVenda --> ContasReceber
PedidoCompra --> ContasPagar

MovimentacaoEstoque --> DRE
ContasReceber --> DRE
ContasPagar --> DRE

@enduml
```
