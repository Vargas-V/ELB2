# APIGateway
Setting up an API Gateway with Kenesis

<h1>Creating an API Gateway with Kenesis</h1>
<div><b>Creation Date:</b> November 29, 2023</div>
<div><b>Created By:</b> Yeison Giraldo</div>

<div style="height: 24px">&#8203;</div>
<hr />
<div style="height: 24px">&#8203;</div>


<div><h3>1. Log in to console and search for IAM</h3>
<p>You will need to create a role to give permissions to the API to talk to Kinesis</p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/429c152c-4a0d-490c-971e-ce77be5de3d0/abd32cb8-d4f7-4ab2-8c53-ae779864bddd.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=170&mark-y=4&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz00ODYmaD0zOSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Log in to console and search for IAM" />
</div>

<div><h3>2. Click on Roles</h3>
<p>Once you are in IAM console click on Roles</p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/9e98e49d-5262-4a01-b6f8-37fab2cba383/8274aed4-ec31-427b-b491-ced3ce50741b.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=29&mark-y=367&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz00MyZoPTI3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Roles" />
</div>

<div><h3>3. Click on Create role</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/1c613821-7b9e-452c-a230-e0efb4107a9f/fef22cd4-7c98-42f8-9051-1dde98119d05.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=956&mark-y=114&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjgmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Create role" />
</div>

<div><h3>4. Click on AWS Service </h3>
<p>In Use Case select API Gateway</p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/266de4ed-6335-433d-8f46-6881eb57c366/9920981c-e883-4704-a899-91f6ef92c26c.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=383&mark-y=772&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz00NjcmaD00MiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on AWS Service " />
</div>

<div><h3>5. Click on Next</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/ab162014-5342-4d6a-82a0-777c9affdd9a/6eeb061e-430c-43b5-8b01-4123d26b68dd.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1021&mark-y=844&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz04NCZoPTQxJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Next" />
</div>

<div><h3>6. Click on Next</h3>
<p>Leave default settings</p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/ad472d2a-29dc-414e-be0a-a5fc486c3b3b/aaec8c69-20a3-4a9e-83d1-0db9a1226da7.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1038&mark-y=430&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz04NCZoPTQxJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Next" />
</div>

<div><h3>7. For Role name Type "tutorial-api-gateway"</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/b637b52c-0089-4386-a980-3a56add34cab/0ee366dc-589f-41bf-87f4-f5b443108aed.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=385&mark-y=285&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz01MjEmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="For Role name Type &quot;tutorial-api-gateway&quot;" />
</div>

<div><h3>8. Click on Create role</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/45dc1554-e9d6-4fa8-89dc-2a47fb9acaf1/a5976e41-b266-4273-9dcb-d036ce78d170.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=977&mark-y=844&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjgmaD00MiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Create role" />
</div>

<div><h3>9. Now we are going to attached a Policy to that role</h3>
<p>Click on tutorial-api-gateway</p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/216da956-7af9-4507-af1e-8a2fc9928af2/cafa2cf5-d60c-4b09-853e-f138ae9f6894.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=400&mark-y=637&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNDImaD0yNyZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Now we are going to attached a Policy to that role" />
</div>

<div><h3>10. Click on Add permissions</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/35152877-2ce3-4b01-ba39-8b8d3f5af0e5/ad3acdb3-4015-4d30-a316-1b3cd4785d62.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=898&mark-y=521&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xODYmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Add permissions" />
</div>

<div><h3>11. Click on Attach policies</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/a1ec2cbb-ff76-4740-9624-3b00b47f89e7/9242f00f-3a01-4c3c-818f-58bcba1cfc2f.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=899&mark-y=555&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOTAmaD0zOSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Attach policies" />
</div>

<div><h3>12. Look for AmazonKinesisAnalyticsFull Access</h3>
<p>Click on the box and then Add permissions</p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/b5f93ecd-2361-467e-a5ed-75928eb33bf2/b86d3a51-a842-4638-a80b-73a6f726f5fd.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=956&mark-y=809&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNjYmaD00MiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Look for AmazonKinesisAnalyticsFull Access" />
</div>

<div><h3>13. Now look for Kinesis</h3>
<p>We need to create a kinesis data stream</p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/4c7d6f42-26cd-4334-abe6-35bbdc2a1895/c0566d67-a505-417f-b9a3-a38697a7d271.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=170&mark-y=4&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz01MDgmaD0zOSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Now look for Kinesis" />
</div>

<div><h3>14. Click on Create data stream</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/973e1f9a-e362-4df4-863b-a78e6cfb4fce/daa68cbc-8c9c-4ff0-9dac-ac22eb6219fe.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=344&mark-y=705&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xODMmaD00MiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Create data stream" />
</div>

<div><h3>15. Give it a name "event-pipe"</h3>
<p>Select Provisioned leave everything else default</p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/7e079d5a-3206-451f-849f-60c0c74b0b60/8314c2e2-6ddd-4c8b-85e2-5e064308b88c.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=503&mark-y=366&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0zNzAmaD0xMDQmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Give it a name &quot;event-pipe&quot;" />
</div>

<div><h3>16. Click on Create data stream</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/f6bffe55-f3d8-40e5-95c7-9625bae36217/6601fc65-9670-4989-b487-70008f347969.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=722&mark-y=844&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xODMmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Create data stream" />
</div>

<div><h3>17. Click on event-pipe…</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/10538e87-08d3-4ca6-b295-0597dcbe679c/c9be5bd6-b119-4997-9fe4-53dd8454fe08.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=283&mark-y=213&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz04NjMmaD03MTQmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on event-pipe…" />
</div>

<div><h3>18. Now we are going to create API Gateway</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/67af9897-5aef-4bf3-bf04-657e99298153/fb900221-3eba-440a-8353-56a84f040617.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=484&mark-y=205&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTQmaD0yNiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Now we are going to create API Gateway" />
</div>

<div><h3>19. Click on Build under REST API</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/84b1a905-0ae4-4034-b10a-708ed790bf25/bc885c17-7ec9-4e97-b0f6-a64879d6e172.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=996&mark-y=718&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz04OCZoPTQyJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Build under REST API" />
</div>

<div><h3>20. Give it a Name "Event-Pipe"</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/19b049a8-ea8f-4449-a361-7acf7f351659/6482e2a2-6e39-4621-8815-be1c9b0fc209.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=98&mark-y=625&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MzYmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Give it a Name &quot;Event-Pipe&quot;" />
</div>

<div><h3>21. Click on Create API</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/f520db1d-a4de-49a9-ab3a-4e78e3029d26/0634710d-750d-47d0-b390-d0e8e0430d1c.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=998&mark-y=842&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjQmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Create API" />
</div>

<div><h3>22. Now that we have the API ready</h3>
<p>We need to create a resouce </p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/a9861462-491c-42a1-8b9d-31bcded2bf1b/fd73655c-73e1-4c5d-bdb5-31bcf0e2108c.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=344&mark-y=331&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNjAmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Now that we have the API ready" />
</div>

<div><h3>23. Give it a name to the resource name "stream"</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/5fa2e854-2bf8-4037-ba6a-fbfb12d417cb/cae41619-1190-45dd-b0d9-1cbc39ec2f82.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=606&mark-y=479&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz00OTYmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Give it a name to the resource name &quot;stream&quot;" />
</div>

<div><h3>24. Click on Create resource</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/5cf60a23-41e5-40b9-9721-fbe189b89a2f/63f38c61-388c-43be-b51e-43ba91973125.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=962&mark-y=616&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNjAmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Create resource" />
</div>

<div><h3>25. Click on API actions</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/53f1e832-ecce-4164-838c-5aaf45ff70b2/8b338edb-0203-4e94-abab-4e8a03aaec3e.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=823&mark-y=274&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNDkmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on API actions" />
</div>

<div><h3>26. Click on Create method</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/6e0e2129-2849-46cf-93db-2620811fb16b/e444149e-e10c-4fd7-b119-c81cc148a70b.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=930&mark-y=669&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNTUmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Create method" />
</div>

<div><h3>27. Method Type Get</h3>
<p>Select AWS Service</p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/98848fd7-366b-4d7b-8055-2a91704c4d91/109ef415-1183-4677-8590-a437a7a99522.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Method Type Get" />
</div>

<div><h3>28. Select Region</h3>
<p>Aws Service Kinesis</p><p>HTTP Method <span data-name="post_office" data-type="emoji">🏣</span> </p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/75207a81-96eb-483a-bfd6-328b59c56152/6b1d4d52-706a-4e98-99d3-5e482b7f5d08.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=98&mark-y=705&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MzYmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Select Region" />
</div>

<div><h2><a href="https://us-east-1.console.aws.amazon.com/apigateway/main/apis/seo9ilhun8/resources/65gmtv/create-method?api=seo9ilhun8&experience=rest&region=us-east-1"># API Gateway - Create method</a></h2></div>

<div><h3>29. Look for the role that was previous Created</h3>
<p>Go to IAM console</p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/471c938c-cf73-4f81-b1b7-da77740724cc/9066136a-f20b-48d7-abaa-955d70e241a8.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=170&mark-y=4&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz00ODYmaD0zOSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Look for the role that was previous Created" />
</div>

<div><h3>30. Click on Roles</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/a3deda19-2fd8-4679-8e3f-8cf2f2d47b08/340fb24e-0b8f-4bf5-8346-b73fd6d0a02e.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=29&mark-y=367&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz00MyZoPTI3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Roles" />
</div>

<div><h3>31. Click on tutorial-api-gateway</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/18f1f0b7-496c-4af0-b67a-cf8d01d364dc/169e074f-34f6-47ca-a970-2e5efc4514ba.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=399&mark-y=629&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNDImaD0yNyZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on tutorial-api-gateway" />
</div>

<div><h3>32. Click on Copy ARN to clipboard</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/644d4613-47d3-4f33-9571-5a95e8d235cd/6caff2ef-f4b6-423f-b9be-ce4654572e80.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=721&mark-y=125&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0zMyZoPTMxJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Copy ARN to clipboard" />
</div>

<div><h3>33. Click on Execution role</h3>
<p>and paste the ARN URL</p>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/50320b17-4ee2-4ebc-9ba2-27b294ac58fb/0e11035b-b92f-4192-b11d-92eef9c86457.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=98&mark-y=705&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MzYmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Execution role" />
</div>

<div><h3>34. Click on Create method</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/c2b67bf3-6ce6-440e-aa82-6a7e4fc47f07/41213ffb-1f11-4490-aa3f-a0242a059c24.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=950&mark-y=842&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNTUmaD00MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Create method" />
</div>

<div><h3>35. Click on Integration request</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/07a1d981-521d-49bf-ae89-5ca09fcf6896/1330a850-ea6a-47de-aa97-f4243cae6d6d.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=843&mark-y=417&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMDImaD0yMCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Integration request" />
</div>

<div><h3>36. Click on Edit</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/b9eacf8e-baef-46bd-b2dd-9936b1af6c3d/c041870e-679c-4b85-8b6c-ccae5fcd421d.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1051&mark-y=147&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02MCZoPTMxJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Edit" />
</div>

<div><h3>37. Click on API Gateway</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/3745d6d7-f980-4240-904f-ff61298e1aee/6c81b677-dbe6-4623-b9e5-202898ebe3d5.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=117&mark-y=195&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02OSZoPTIwJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on API Gateway" />
</div>

<div><h3>38. Click on Event-Pipe</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/e4c7918a-1b50-4132-9cf1-4092439057f3/a8922d2f-5647-4a9f-8e4b-816dcc30fe22.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=306&mark-y=257&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02MCZoPTIwJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Event-Pipe" />
</div>

<div><h3>39. Click on GET</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/65a2a3db-c30b-43b3-8759-a6a7b2b2da33/48773fe9-ea6f-4a97-9eaf-43308bd19acb.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=301&mark-y=307&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNTcmaD0yNCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on GET" />
</div>

<div><h3>40. Click on Deploy API Gateway</h3>
<img src="https://images.tango.us/workflows/9d8443d6-f996-4991-803c-a85ece1e38ed/steps/2b429ec2-5382-4ca6-863c-ed638e8460a8/c2111b9c-a952-472e-8433-64d6d2cf33d9.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5728&fp-y=0.5688&fp-z=1.1654&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=54&mark-y=2&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMDk4Jmg9NzA5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on Deploy API Gateway" />
</div>

<div><h2># This are the basic steps to configure an API Gateway with Kinesis</h2><p>You will need to continue configuring the API Gateway with your code to do data transformation and more.</p>
</div>

<br/>
<hr/>
<div>

</div>
