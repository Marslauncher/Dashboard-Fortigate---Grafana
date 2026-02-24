# Fortigate 40F Dashboard for Grafana

Este repositório contém um dashboard avançado para monitoramento de firewalls **Fortigate 40F**, utilizando o **Zabbix**. O painel foi desenhado para oferecer uma visão clara tanto do hardware quanto da saúde dos links de internet (SD-WAN) e túneis VPN.

<img width="1910" height="1040" alt="image" src="https://github.com/user-attachments/assets/258af2f5-2222-4320-bdc2-5e8dd9d3bf0e" />


## O que está sendo monitorado?

O dashboard está dividido em seções estratégicas para facilitar a administração de rede:

* **Identidade Visual & Status:** Cabeçalho customizado e representação visual das portas físicas do Fortigate 40F.
* **Recursos de Hardware:** * Uso de CPU (com gráfico dinâmico ECharts).
    * Consumo de Memória RAM.
    * Uptime do sistema.
* **Conectividade & SD-WAN:**
    * Latência ICMP em tempo real para múltiplos links (ex: Starlink, Valenet).
    * Histórico de status de conectividade (Status History).
    * Tráfego de interface (Download/Upload) detalhado por link.
* **Túneis VPN:** Monitoramento de status (Online/Offline) de túneis Site-to-Site.
* **Saúde da Rede:** Detecção de erros de pacotes em interfaces específicas (Inbound/Outbound errors).

## Pré-requisitos

Para que o dashboard funcione corretamente, você precisará de:

1.  **Zabbix Server** com o Fortigate 40F já cadastrado via SNMP (utilizando templates padrão Fortinet).
2.  **Plugins no Grafana:**
    * [Zabbix Data Source](https://grafana.com/grafana/plugins/alexanderzobnin-zabbix-datasource/)
    * [ECharts Panel](https://grafana.com/grafana/plugins/volkovlabs-echarts-panel/) (usado no gráfico de CPU)
    * [Business Text (opcional)](https://grafana.com/grafana/plugins/marcusolsson-static-datasource/) (para o cabeçalho HTML)

## Como Instalar (Passo a Passo)

1.  **Baixe o arquivo JSON:** * Faça o download do arquivo `Fortigate-40F.json` presente neste repositório.
2.  **No seu Grafana:**
    * Vá em **Dashboards** -> **New** -> **Import**.
    * Clique em **Upload JSON file** e selecione o arquivo baixado.
3.  **Configuração de Data Source:**
    * Na tela de importação, o Grafana solicitará que você selecione a fonte de dados. Selecione o seu **Zabbix Data Source**.
    * Certifique-se de que os nomes dos *Hosts* e *Groups* no seu Zabbix batem com os filtros do dashboard (ou ajuste os filtros após importar).
4.  **Ajustes Finais:**
    * Caso os gráficos de interface apareçam vazios, verifique se o nome das interfaces no seu Fortigate condiz com as métricas (ex: `lan3`, `wan1`).

## Contribuições

Sinta-se à vontade para abrir uma **Issue** se encontrar algum bug ou enviar um **Pull Request** com melhorias. Feedbacks sobre novos painéis para SD-WAN ou regras de firewall são muito bem-vindos!

---
Documentação gerada para a comunidade de administradores de redes. 🚀
