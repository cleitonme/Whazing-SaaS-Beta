# **Como USAR API DO WHAZING**

---

Atualmente a API funciona com o canal WhatsApp bayles

- externalkey - Identificador único para cada mensagem, pode ser qualquer valor e aparece no webhook na apiConfig

---

## **1. Segue arquivo postman**

- Faça o [download do arquivo modelo](apiizing.json)

---

# Manual de Uso da API Whazing

![print](whazing.png)

## Índice
1. Autenticação
2. Endpoints Disponíveis
3. Exemplos de Uso
4. Códigos de Exemplo

## 1. Autenticação

Todas as requisições devem incluir o token Bearer no header de autenticação:

```
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

## 2. Endpoints Disponíveis

Base URL: `https://testeapi.whazing.com.br/v1/api/external/d6747d15-7346-4047-97f4-247f6ce45585`

### 2.1 Mensagens

#### a) Enviar Mensagem de Texto
- **Endpoint**: `/`
- **Método**: POST
- **Content-Type**: application/json

```json
{
    "body": "Sua mensagem aqui",
    "number": "5511999999999",
    "externalKey": "ID_UNICO_SISTEMA"
}
```

#### b) Enviar Mensagem com Arquivo
- **Endpoint**: `/`
- **Método**: POST
- **Content-Type**: multipart/form-data

Parâmetros:
- media (arquivo)
- body (texto)
- number (telefone)
- externalKey (identificador único)(opcional)

### 2.2 Contatos

#### a) Criar Contato
- **Endpoint**: `/createcontact`
- **Método**: POST

```json
{
  "name": "João Silva",
  "number": "5511987654321",
  "email": "joao.silva@exemplo.com",
  "extraInfo": [
    {
      "name": "Empresa",
      "value": "Exemplo Ltda"
    }
  ],
  "wallets": [],
  "disableBot": false,
  "disableCampaign": false,
  "commentary": "Cliente VIP",
  "deadline": "2023-12-31T23:59:59Z",
  "disableKanban": false,
  "kanbanPrice": "1500",
  "ignore": false
}
```

#### b) Consultar Contato
- **Endpoint**: `/contact`
- **Método**: POST

Por número:
```json
{
  "number": "5511999999999"
}
```

Por ID:
```json
{
  "contactId": 3397
}
```

### 2.3 Tickets

#### a) Criar Ticket
- **Endpoint**: `/createticket`
- **Método**: POST

```json
{
  "number": "5511999999999",
  "status": "pending",
  "queueId": 4,
  "userId": null
}
```

#### b) Consultar Ticket
- **Endpoint**: `/showticket`
- **Método**: POST

```json
{
  "number": "5511999999999"
}
```

#### c) Atualizar Ticket
- **Endpoint**: `/updateticketinfo`
- **Método**: POST

```json
{
  "ticketId": 1003,
  "status": "open",
  "userId": 1,
  "queueId": null
}
```

### 2.4 Mensagens Interativas (API Oficial)

#### a) Mensagem com Botões
- **Endpoint**: `/apioficial`
- **Método**: POST

```json
{
    "number": "5511999999999",
    "contents": {
        "type": "button",
        "body": {
            "text": "Texto do Botão"
        },
        "action": {
            "buttons": [
                {
                    "type": "reply",
                    "reply": {
                        "id": "1",
                        "title": "Botão 1"
                    }
                }
            ]
        }
    }
}
```

#### b) Mensagem com Lista
- **Endpoint**: `/apioficial`
- **Método**: POST

```json
{
  "number": "5511999999999",
  "contents": {
    "type": "list",
    "header": {
      "type": "text",
      "text": "Título"
    },
    "body": {
      "text": "Descrição"
    },
    "action": {
      "sections": [
        {
          "title": "Lista 1",
          "rows": [
            {
              "id": 1,
              "title": "Linha 1",
              "description": "Descrição da linha 1"
            }
          ]
        }
      ],
      "button": "Clique aqui"
    }
  }
}
```

#### c) Mensagem com Link (CTA)
- **Endpoint**: `/apioficial`
- **Método**: POST

```json
{
    "number": "5511999999999",
    "contents": {
        "type": "cta_url",
        "header": {
            "type": "text",
            "text": "Título"
        },
        "body": {
            "text": "Descrição"
        },
        "footer": {
            "text": "Rodapé"
        },
        "action": {
            "name": "cta_url",
            "parameters": {
                "display_text": "Ver Mais",
                "url": "SEU_LINK"
            }
        }
    }
}
```

### 2.5 Templates

#### a) Template Simples
- **Endpoint**: `/apioficial`
- **Método**: POST

```json
{
    "number": "5511999999999",
    "contents": {
        "name": "nome_do_template",
        "components": [{
            "type": "body",
            "parameters": []
        }],
        "language": {
            "code": "pt_BR"
        }
    }
}
```

### 2.6 Outros Endpoints

#### a) Validar Número WhatsApp
- **Endpoint**: `/valid-whatsapp-number`
- **Método**: POST

```json
{
  "number": "5511999999999"
}
```

#### b) Status do Canal
- **Endpoint**: `/statuschannel`
- **Método**: GET

#### c) QR Code
- **Endpoint**: `/qrcode`
- **Método**: POST

```json
{
  "number": null
}
```

## 3. Exemplos de Código

### Python
```python
import requests
import json

class WhazingAPI:
    def __init__(self, base_url, token):
        self.base_url = base_url
        self.headers = {
            'Authorization': f'Bearer {token}',
            'Content-Type': 'application/json'
        }

    def send_message(self, number, body, external_key):
        payload = {
            'number': number,
            'body': body,
            'externalKey': external_key
        }
        response = requests.post(self.base_url, 
                               headers=self.headers, 
                               json=payload)
        return response.json()

    def send_file(self, number, file_path, body, external_key):
        files = {
            'media': open(file_path, 'rb'),
            'body': (None, body),
            'number': (None, number),
            'externalKey': (None, external_key)
        }
        headers = {'Authorization': f'Bearer {token}'}
        response = requests.post(self.base_url, 
                               headers=headers, 
                               files=files)
        return response.json()

# Exemplo de uso
api = WhazingAPI(
    'https://testeapi.whazing.com.br/v1/api/external/d6747d15-7346-4047-97f4-247f6ce45585',
    'seu-token-aqui'
)

# Enviar mensagem
result = api.send_message('5511999999999', 'Olá, mundo!', 'TEST123')
```

### Node.js
```javascript
const axios = require('axios');
const FormData = require('form-data');
const fs = require('fs');

class WhazingAPI {
    constructor(baseUrl, token) {
        this.baseUrl = baseUrl;
        this.token = token;
    }

    async sendMessage(number, body, externalKey) {
        try {
            const response = await axios.post(
                this.baseUrl,
                {
                    number,
                    body,
                    externalKey
                },
                {
                    headers: {
                        'Authorization': `Bearer ${this.token}`,
                        'Content-Type': 'application/json'
                    }
                }
            );
            return response.data;
        } catch (error) {
            throw error;
        }
    }

    async sendFile(number, filePath, body, externalKey) {
        const form = new FormData();
        form.append('media', fs.createReadStream(filePath));
        form.append('body', body);
        form.append('number', number);
        form.append('externalKey', externalKey);

        try {
            const response = await axios.post(
                this.baseUrl,
                form,
                {
                    headers: {
                        'Authorization': `Bearer ${this.token}`,
                        ...form.getHeaders()
                    }
                }
            );
            return response.data;
        } catch (error) {
            throw error;
        }
    }
}

// Exemplo de uso
const api = new WhazingAPI(
    'https://testeapi.whazing.com.br/v1/api/external/d6747d15-7346-4047-97f4-247f6ce45585',
    'seu-token-aqui'
);

// Enviar mensagem
api.sendMessage('5511999999999', 'Olá, mundo!', 'TEST123')
    .then(response => console.log(response))
    .catch(error => console.error(error));
```

### PHP
```php
<?php

class WhazingAPI {
    private $baseUrl;
    private $token;

    public function __construct($baseUrl, $token) {
        $this->baseUrl = $baseUrl;
        $this->token = $token;
    }

    public function sendMessage($number, $body, $externalKey) {
        $curl = curl_init();
        
        $data = [
            'number' => $number,
            'body' => $body,
            'externalKey' => $externalKey
        ];

        curl_setopt_array($curl, [
            CURLOPT_URL => $this->baseUrl,
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_POST => true,
            CURLOPT_POSTFIELDS => json_encode($data),
            CURLOPT_HTTPHEADER => [
                'Authorization: Bearer ' . $this->token,
                'Content-Type: application/json'
            ]
        ]);

        $response = curl_exec($curl);
        curl_close($curl);

        return json_decode($response, true);
    }

    public function sendFile($number, $filePath, $body, $externalKey) {
        $curl = curl_init();
        
        $data = [
            'media' => new CURLFile($filePath),
            'body' => $body,
            'number' => $number,
            'externalKey' => $externalKey
        ];

        curl_setopt_array($curl, [
            CURLOPT_URL => $this->baseUrl,
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_POST => true,
            CURLOPT_POSTFIELDS => $data,
            CURLOPT_HTTPHEADER => [
                'Authorization: Bearer ' . $this->token
            ]
        ]);

        $response = curl_exec($curl);
        curl_close($curl);

        return json_decode($response, true);
    }
}

// Exemplo de uso
$api = new WhazingAPI(
    'https://testeapi.whazing.com.br/v1/api/external/d6747d15-7346-4047-97f4-247f6ce45585',
    'seu-token-aqui'
);

// Enviar mensagem
$result = $api->sendMessage('5511999999999', 'Olá, mundo!', 'TEST123');
print_r($result);

## 4. Observações Importantes

1. Todos os números devem estar no formato DDI+DDD+NÚMERO (ex: 5511999999999)
2. O token de autenticação deve ser mantido em segurança
3. Para mensagens em grupo, use o formato "nome-do-grupo@grupo" no campo number
4. Os templates devem ser previamente aprovados pelo WhatsApp
5. Mantenha o externalKey único para cada mensagem para rastreamento

Para casos específicos ou dúvidas adicionais, consulte a documentação completa ou entre em contato com o suporte.