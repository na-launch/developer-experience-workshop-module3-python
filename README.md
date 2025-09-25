# 🚀 **Module 3: Managing Your Container Workspace**

**Technology Stack:**

- Python
- DevSpaces
- Kafka  

---

## 🎯 **Scenario**

Inside this workspace is a Python Application that connects to an Openshift Kafka Cluster. There are 3 commands you can run from within the application.

  ```python
  # Run the producer
  python producer.py --topic <name_of_topic>
  ```

  ```python
  # Run the consumer
  python consumer.py --topic <name_of_topic>
  ```

  ```python
  # Run the WebAPP
  uvicorn main:app --host 0.0.0.0 --port 8000 --reload
  ```

---

## 🐾 **Guided Walkthrough**

The application has some problems that we would like you to fix:

1. Run `pip install -r requirements.txt` to install the necessary dependencies
2. Set the `KAFKA_BOOTSTRAP_SERVERS` environment variable based on the kafka cluster you created
3. In a separate browser window open: https://devfile.io/docs/2.3.0/quickstart-che as a reference
4. Create a new devfile (devfile.yaml) in the project root
  - 4.1. Point to the python UDI image - registry.access.redhat.com/ubi9/python-39:1-1739420387 
  - 4.2. Configure memory and CPU
  - 4.3. Do not rely on CLI Anymore!
    - 4.3.1. Create a build task for installation
    - 4.3.2. Create a run task for consumer.py
    - 4.3.3. Create a run task for producer.py 
    - 4.3.4. Create a run task for main.py
  - 4.4. Set the `KAFKA_BOOTSTRAP_SERVERS` environment variable to the kafka instance you created
5. Create a new topic in the producer command named `today`
  - 5.1. Add 7-8 messages in there
6. Run the consumer command and point the topic to `today`
  - 6.1. Verify messages are funneling through
7. Run the web application (if you have built a command for main.py you can use that)
  - 7.1. In the topics input, put `today` and verify messages are funnelling through

---

## 🧩 **Challenge**

- [ ] Add your devfile tasks to the tasks.json
- [ ] Load 3 python extensions into a `.vscode/extensions.json` file
- [ ] Write a few small unit tests using mocks for the Kafka producer to verify that your logic (like input handling and retry mechanisms) works as expected without needing a real Kafka cluster.

---

## 🥚 **Easter Eggs!**

- [ ] There is an easter egg in the code
  - Be thorough! Look through the code.

---

## ✅ **Key Takeaways**

- Built your first devfile!
- Configured your devspaces / odo workspace
- Customized your vscode environment
- First Interaction with Streams for Apache Kafka
- Introductory patterns around Event Driven Architecture
