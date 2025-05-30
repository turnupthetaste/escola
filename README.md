# escola



C:\Users\felip_gzsen7w>curl -X POST http://localhost:3000/professor -H "Content-Type: application/json" -d "{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\": \"07494812857\"}"
curl: (7) Failed to connect to localhost port 3000 after 2256 ms: Could not connect to server

C:\Users\felip_gzsen7w>curl -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\": \"07494812857\"}"
{"nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","_id":"6838ed809e0b3c0b354a814e","__v":0}

C:\Users\felip_gzsen7w>curl -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\": \"07494812857\"}"
{"message":"CPF ou e-Mail já em uso"}

C:\Users\felip_gzsen7w>curl -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"nome\": \"Carlos Silva\", \"email\": \"carlos.silva@fatec.sp.gov.br\", \"cpf\": \" 63479695051\"}"
{"nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","_id":"6838f2279e0b3c0b354a8152","__v":0}
C:\Users\felip_gzsen7w>curl -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"nome\": \"Odete Roitman\", \"email\": \"odete.roitman@fatec.sp.gov.br\", \"cpf\": \" 32082128016\"}"
{"nome":"Odete Roitman","email":"odete.roitman@fatec.sp.gov.br","cpf":"32082128016","_id":"6838f2469e0b3c0b354a8154","__v":0}

C:\Users\felip_gzsen7w>curl -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\": \"07494812857\"}"
{"message":"CPF ou e-Mail já em uso"}

C:\Users\felip_gzsen7w>curl -X POST http://localhost:3000/professor -H "Content-Type: application/json" -d "{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\": \"12345678910\"}"
{"message":"12345678910 não é um CPF válido"}

C:\Users\felip_gzsen7w>curl -X POST http://localhost:3000/professor -H "Content-Type: application/json" -d "{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec\", \"cpf\": \"12345678910\"}"
{"message":"henrique.louro@fatec não é um formato de e-mail válido"}

C:\Users\felip_gzsen7w>curl -X GET http://localhost:3000/professor
[{"_id":"6838ed809e0b3c0b354a814e","nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","__v":0},{"_id":"6838f2279e0b3c0b354a8152","nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","__v":0},{"_id":"6838f2469e0b3c0b354a8154","nome":"Odete Roitman","email":"odete.roitman@fatec.sp.gov.br","cpf":"32082128016","__v":0}]

C:\Users\felip_gzsen7w>curl -X PUT http://localhost:3000/professor -H "Content-Type: application/json" -d "{\"id\":\"6838f2469e0b3c0b354a8154\",\"nome\": \"Odetinha Roitman\", \"email\": \"odetinha.roitman@fatec.sp.gov.br\", \"cpf\": \" 32082128016\"}"
{"_id":"6838f2469e0b3c0b354a8154","nome":"Odetinha Roitman","email":"odetinha.roitman@fatec.sp.gov.br","cpf":"32082128016","__v":0}

C:\Users\felip_gzsen7w>curl -X DELETE http://localhost:3000/professor -H "Content-Type: application/json" -d "{\"id\":\"6838f2469e0b3c0b354a8154\"}"

{"message":"Professor excluído com sucesso"}
C:\Users\felip_gzsen7w>curl -X GET http://localhost:3000/professor
[{"_id":"6838ed809e0b3c0b354a814e","nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","__v":0},{"_id":"6838f2279e0b3c0b354a8152","nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","__v":0}]

C:\Users\felip_gzsen7w>curl -X POST http://localhost:3000/disciplina -H "Content-Type: application/json" -d "{\"descricao\": \"Técnicas de Programação II\"}"
{"descricao":"Técnicas de Programação II","_id":"6838f4862f6df2fb825754ba","__v":0}

C:\Users\felip_gzsen7w>curl -X POST http://localhost:3000/disciplina -H "Content-Type: application/json" -d "{\"descricao\": \"Lógica de Programação\"}"
{"descricao":"Lógica de Programação","_id":"6838f4a42f6df2fb825754bc","__v":0}

C:\Users\felip_gzsen7w>curl -X GET http://localhost:3000/disciplina
[{"_id":"6838f4a42f6df2fb825754bc","descricao":"Lógica de Programação","__v":0},{"_id":"6838f4862f6df2fb825754ba","descricao":"Técnicas de Programação II","__v":0}]

C:\Users\felip_gzsen7w>curl -X POST http://localhost:3000/professor_has_disciplina -H "Content-Type: application/json" -d "{\"professor\": \"6838ed809e0b3c0b354a814e\", \"disciplina\": \"6838f4862f6df2fb825754ba\"}"
{"professor":"6838ed809e0b3c0b354a814e","disciplina":"6838f4862f6df2fb825754ba","_id":"6838f5512f6df2fb825754bf","__v":0}

C:\Users\felip_gzsen7w>curl -X POST http://localhost:3000/professor_has_disciplina -H "Content-Type: application/json" -d "{\"professor\": \"6838f2279e0b3c0b354a8152\", \"disciplina\": \"6838f4a42f6df2fb825754bc\"}"
{"professor":"6838f2279e0b3c0b354a8152","disciplina":"6838f4a42f6df2fb825754bc","_id":"6838f5952f6df2fb825754c3","__v":0}

C:\Users\felip_gzsen7w>curl -X GET http://localhost:3000/professor_has_disciplina
[{"_id":"6838f5512f6df2fb825754bf","professor":{"_id":"6838ed809e0b3c0b354a814e","nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","__v":0},"disciplina":{"_id":"6838f4862f6df2fb825754ba","descricao":"Técnicas de Programação II","__v":0}},{"_id":"6838f5952f6df2fb825754c3","professor":{"_id":"6838f2279e0b3c0b354a8152","nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","__v":0},"disciplina":{"_id":"6838f4a42f6df2fb825754bc","descricao":"Lógica de Programação","__v":0}}]
C:\Users\felip_gzsen7w>

