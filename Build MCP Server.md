
#linkedIn #AI 

I just build a MCP server in 10 mins.
This is possible due to Spring AI,
Here's how you can build it.



Step 1: Create a Spring Boot Application and builkd a service Layer which can business logic and can expose some data.

eg:

public List<Match> getAllMatches() {  
    return matches;  
}



Step 2: Add the MCP server dependency in your POM.xml file


<dependency>  
    <groupId>org.springframework.ai</groupId>  
    <artifactId>spring-ai-starter-mcp-server</artifactId>  
</dependency>


Step 3: Annotate your Methods with Tool annotataion to expose a method as MCP Tool.


@Tool(description = "Get all matches for IPL 2025")
public List<Match> getAllMatches() {  
    return matches;  
}


Step 4: Register all the tools which can be exposed.

@Bean
public ToolCallbackProvider weatherTools(ScheduleService scheduleService) {
	return MethodToolCallbackProvider.builder().toolObjects(scheduleService).build();
}



Step 5: Disable Spring Banner and Logs from Console in application.properties


spring.main.banner-mode=off  
logging.file.name=mcp-server.log  
logging.pattern.console=


Step 6: Build the MCP Server

mvn clean package


Step 7: Configure your MCP Server with your MCP Host.

Lets configure in Claude Desktop.

Go to Library/Application Support/Claude
create claude_desktop_config.json file and add the server config.

{
"mcpServers": {
  "ipl-schedule-api-mcp-server": {
    "command": "/opt/homebrew/opt/openjdk@21/bin/java",
    "args": [
      "-jar",
      "/target/ipl-schedule-api-mcp-server-0.0.1-SNAPSHOT.jar"
    ]
  }
}
}



Thats it. You just created your MCP server and it is ready to use.

You can check out complete tutorial on my Youtube Channel for in-depth guide.

Save 💾 ➞ React 👍 ➞ Share ♻️  
  
& follow for everything related to System Design & Engineering