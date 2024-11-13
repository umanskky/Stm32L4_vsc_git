Доп. настройки для VSC

- Для генерации .bin и .hex - необходимо добавить в CMakeLists.txt:

  //*********************************************
  # Convert output to hex and binary
  add_custom_command(TARGET ${CMAKE_PROJECT_NAME} POST_BUILD
    COMMAND ${CMAKE_OBJCOPY} -O ihex $<TARGET_FILE:${CMAKE_PROJECT_NAME}> ${CMAKE_PROJECT_NAME}.hex
    )

  # Convert to bin file -> add conditional check?
  add_custom_command(TARGET ${CMAKE_PROJECT_NAME} POST_BUILD
    COMMAND ${CMAKE_OBJCOPY} -O binary $<TARGET_FILE:${CMAKE_PROJECT_NAME}> ${CMAKE_PROJECT_NAME}.bin
  )
  //*********************************************
  
- Для работы дебагера на MAC, смотрим инструкцию (почти конец видео, где прописываем пути вручную на патчи):
  ссылка: https://www.youtube.com/watch?v=JogKig9NUiM
