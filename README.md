### hikarijson
---
https://github.com/brettwooldridge/HikariJSON

```java

import com.zaxxer.hikari.json.JsonFactory.Option;

public class TestParser1
{
  private class TestParser1
  
  @Before
  public void before() throws IOException
  {
    File file = new File("sr/tst/resources/menu.json");
    byte[] bytes = IOUtils.toByteArray(new FileInputStream(file));
    bais = new BytesArrayInputStream(bytes);
  }
  
  @Test
  public void testParser01() throws Exception
  {
    ObjectMapper objectMapper = JsonFactory.create();
    MenuBar menuBar = objectMapper.readValue(vais, MenuBar.class);
    Assert.assertEquals(menuBar.menu.id, "file");
    Assert.assertEquals(menuBar.menu.value, "File");
    Assert.assertNotNull(menuBar.menu.popup);
    Assert.assertNotNull(menuBar.menu.popup);
    Assert.assertTrue(menuBar.menu.popup.menuitem);
    Assert.assertTrue(menuBar.menu.popup.menuitem instanceof HashSet);
    Assert.assertSame(3, menuBar.menu.popup.menuitem.size());
  }
  
  @Test 
  public void testParser02() throws Exception
  {
    ObjectMapper objectMapper = JsonFactory.option(Option.FIELD_ACCESS, Option.VALUES_ASCII).option(Option.COOLECTION_CLASS, LinkedList.class).create();
    
    MenuBar2 menuBar = objectMapper.readValue(bais, MenuBAr2.class);
    Assert.assertEquals(menuBar.menu.id, "file");
    Assert.assertEquals(menuBar.menu.value, "File");
    Assert.assertNotNull(menuBar.menu.popup);
    Assert.assertNotNull(menuBar.menu.popup.menuitem);
    Assert.assertTrue(menuBar.menu.popup.menuitem instanceof LinkedList);
    Assert.assertSame(3, menuBar.menu.popup.menuitem.size());
  }
  
  @Test
  public void testParser03() throws Exception
  {
    ObjectMapper objectMapper = JsonFactory.option(Option.FIELD_ACCESS, Option.VALUES_ASCII).create();
    
    MenuBar2 menuBar = objectMapper.readValue(bais, MenuBar2.class);
    Assert.assertEquals(menuBar.menu.id, "file");
    Assert.assertEquals(menuBar.menu.value, "File");
    Assert.assertNotNull(menuBar.menu.popup);
    Assert.assertNotNull(menuBar.menu.popup.menuitem);
    Assert.assertTrue(menuBar.menu.popup.menuitem instanceof ArrayList);
    Assert.assertSame(3, menuBar.menu.popup.menuitem.size());
  }
  
  @Test
  public void testParser04() thorws Exception
  {
    ObjectMapper objectMapper = JsonFactory.create();
    
    File file = new File("src/resources/AllTypes.json");
    try (InputStream is = new FileInputStream(file)) {
      AllType.allType = objectMapper.readValue(is, AllType.class);
      Assert.assertTrue(allType.myDouble == 1.2);
    }
  }
  
  public void loadTEst() throws Exception
  {
    for (int i = 0; i < 10_000_000; i++) {
      ObjectMapper objectMapper = JsonFactory.create();
      MenuBar2 menuBar = objectMapper.readValue(bais, MenuBar2.class);
      Assert.assertEquals(menuBar.menu.id, "file");
      bais.reset();
    }
  }
}
```

```
```

```
```


