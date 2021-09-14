
https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-web-api?view=aspnetcore-5.0&tabs=visual-studio-code



//POSTMAN collection

{
	"info": {
		"_postman_id": "4db16ccf-8d99-4494-b375-ecff156709dc",
		"name": "TodoAPI",
		"schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
	},
	"item": [
		{
			"name": "Create new todo item (201)",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"pm.test(\"Status code is 201\", function () {\r",
							"    pm.response.to.have.status(201);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\r\n  \"name\":\"walk dog\",\r\n  \"isComplete\":true\r\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "https://localhost:5001/api/todoitems",
					"protocol": "https",
					"host": [
						"localhost"
					],
					"port": "5001",
					"path": [
						"api",
						"todoitems"
					]
				}
			},
			"response": []
		},
		{
			"name": "Create another new todo item",
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\r\n  \"name\":\"buy milk\",\r\n  \"isComplete\":true\r\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "https://localhost:5001/api/todoitems",
					"protocol": "https",
					"host": [
						"localhost"
					],
					"port": "5001",
					"path": [
						"api",
						"todoitems"
					]
				}
			},
			"response": []
		},
		{
			"name": "Retrieve todo items ID 1 (200)",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});\r",
							"\r",
							"pm.test(\"Check return data content\", function () {\r",
							"    var jsonData = pm.response.json();\r",
							"    pm.expect(jsonData.id).to.eql(1);\r",
							"    pm.expect(jsonData.name).to.eql(\"walk dog\");\r",
							"    pm.expect(jsonData.isComplete).to.eql(true);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://localhost:5001/api/TodoItems/1",
					"protocol": "https",
					"host": [
						"localhost"
					],
					"port": "5001",
					"path": [
						"api",
						"TodoItems",
						"1"
					]
				}
			},
			"response": []
		},
		{
			"name": "Retrieve todo items ID 1 (200) new data",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});\r",
							"\r",
							"pm.test(\"Check return data content\", function () {\r",
							"    var jsonData = pm.response.json();\r",
							"    pm.expect(jsonData.id).to.eql(1);\r",
							"    pm.expect(jsonData.name).to.eql(\"feed fish\");\r",
							"    pm.expect(jsonData.isComplete).to.eql(true);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://localhost:5001/api/TodoItems/1",
					"protocol": "https",
					"host": [
						"localhost"
					],
					"port": "5001",
					"path": [
						"api",
						"TodoItems",
						"1"
					]
				}
			},
			"response": []
		},
		{
			"name": "Retrieve todo items ID 1 (404)",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"pm.test(\"Status code is 404\", function () {\r",
							"    pm.response.to.have.status(404);\r",
							"});\r",
							""
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://localhost:5001/api/TodoItems/1",
					"protocol": "https",
					"host": [
						"localhost"
					],
					"port": "5001",
					"path": [
						"api",
						"TodoItems",
						"1"
					]
				}
			},
			"response": []
		},
		{
			"name": "Retrieve todo items ID 1 (404) Copy",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"pm.test(\"Status code is 404\", function () {\r",
							"    pm.response.to.have.status(404);\r",
							"});\r",
							""
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://localhost:5001/api/TodoItems/1",
					"protocol": "https",
					"host": [
						"localhost"
					],
					"port": "5001",
					"path": [
						"api",
						"TodoItems",
						"1"
					]
				}
			},
			"response": []
		},
		{
			"name": "Get all todoitems",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});\r",
							"\r",
							"pm.test(\"Check return data content\", function () {\r",
							"    var jsonData = pm.response.json();\r",
							"    pm.expect(jsonData[0].id).to.eql(1);\r",
							"    pm.expect(jsonData[0].name).to.eql(\"walk dog\");\r",
							"    pm.expect(jsonData[0].isComplete).to.eql(true);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://localhost:5001/api/todoitems",
					"protocol": "https",
					"host": [
						"localhost"
					],
					"port": "5001",
					"path": [
						"api",
						"todoitems"
					]
				}
			},
			"response": []
		},
		{
			"name": "Update todoitem ID 1 (204)",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"pm.test(\"Status code is 204\", function () {\r",
							"    pm.response.to.have.status(204);\r",
							"});\r",
							""
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "PUT",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\r\n    \"id\": 1,\r\n    \"name\": \"feed fish\",\r\n    \"isComplete\": true\r\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "https://localhost:5001/api/TodoItems/1",
					"protocol": "https",
					"host": [
						"localhost"
					],
					"port": "5001",
					"path": [
						"api",
						"TodoItems",
						"1"
					]
				}
			},
			"response": []
		},
		{
			"name": "Delete todoitem ID 1 (204)",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"pm.test(\"Status code is 204\", function () {\r",
							"    pm.response.to.have.status(204);\r",
							"});\r",
							""
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "DELETE",
				"header": [],
				"url": {
					"raw": "https://localhost:5001/api/TodoItems/1",
					"protocol": "https",
					"host": [
						"localhost"
					],
					"port": "5001",
					"path": [
						"api",
						"TodoItems",
						"1"
					]
				}
			},
			"response": []
		}
	]
}
