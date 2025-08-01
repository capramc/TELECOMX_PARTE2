# TELECOMX_PARTE2

## DESAFIO
Desenvolver modelos preditivos capazes de prever quais clientes têm maior chance de cancelar os serviços oferecidos pela TelecomX.

A empresa quer antecipar o problema da evasão, e cabe a você construir um pipeline robusto para essa etapa inicial de modelagem.

### Preparação dos Dados
Carregue o arquivo CSV que contém os dados tratados anteriormente. 
<table>
 <tr><td align=center>Variável</td><td align=center>Possíveis Valores</td><td align=center>Significado</td></tr>
 <tr><td>customerID</td><td align=center>Letras e Números</td><td>Identificador do cliente</td></tr>
 
 <tr><td>Churn</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 
 <tr><td>gender</td><td align=center>0 ou 1</td><td align=center>Female | Male</td></tr>
  
 <tr><td>SeniorCitizen</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>

 <tr><td>Partner</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 
 <tr><td>Dependents</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 
 <tr><td>tenure</td><td align=center>número de meses</td><td align=center>número</td></tr>

 <tr><td>PhoneService</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 
 <tr><td>MultipleLines_No</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>MultipleLines_Yes</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>MultipleLines_No_phone_service</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>

 <tr><td>InternetService_DSL</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>InternetService_Fiber_optic</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>InternetService_No</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 
 <tr><td>OnlineSecurity_No</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>OnlineSecurity_No_internet_service</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>OnlineSecurity_Yes</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>

 <tr><td>OnlineBackup_No</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>OnlineBackup_No_internet_service</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>OnlineBackup_Yes</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>

 <tr><td>DeviceProtection_No</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>DeviceProtection_No_internet_service</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>DeviceProtection_Yes</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>

 <tr><td>TechSupport_No</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>TechSupport_No_internet_service</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>TechSupport_Yes</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>

 <tr><td>StreamingTV_No</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>StreamingTV_No_internet_service</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>StreamingTV_Yes</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr> 

 <tr><td>StreamingMovies_No</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>StreamingMovies_No_internet_service</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>StreamingMovies_Yes</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr> 

 <tr><td>Contract_One_year</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>Contract_Two_year</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>Contract_Month_to_month</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr> 

 <tr><td>PaperlessBilling</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>

 <tr><td>PaymentMethod_Mailed_check</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>PaymentMethod_Electronic_check</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr>
 <tr><td>PaymentMethod_Credit_card_(automatic)</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr> 
 <tr><td>PaymentMethod_Bank_transfer_(automatic)</td><td align=center>0 ou 1</td><td>0 -> No | 1 -> Yes</td></tr> 

 <tr><td>Charges_Monthly</td><td align=center>número</td><td>valor cobrado por mês</td></tr>
 <tr><td>Charges_Total</td><td align=center>número</td><td>valor cobrado no total</td></tr>
 <tr><td>Daily_Charge</td><td align=center>número</td><td>valor cobrado por dia</td></tr>

 
  
</table>
