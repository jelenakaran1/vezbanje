################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
zadatak1.b.lss \

FLASH_IMAGE += \
zadatak1.b.hex \

SIZEDUMMY += \
sizedummy \

AVRDUDEDUMMY += \
avrdudedummy \


# All Target
all: zadatak1.b.elf secondary-outputs

# Tool invocations
zadatak1.b.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,zadatak1.b.map -mmcu=atmega328p -o "zadatak1.b.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

zadatak1.b.lss: zadatak1.b.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S zadatak1.b.elf  >"zadatak1.b.lss"
	@echo 'Finished building: $@'
	@echo ' '

zadatak1.b.hex: zadatak1.b.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex zadatak1.b.elf  "zadatak1.b.hex"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: zadatak1.b.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega328p zadatak1.b.elf
	@echo 'Finished building: $@'
	@echo ' '

avrdudedummy: zadatak1.b.elf
	@echo 'Invoking: AVRDude'
	C:\Users\Jelena\Desktop\FTN\eclipse\eclipse\bin\avrdude -pm328p -Uflash:w:zadatak1.b.hex:a
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(AVRDUDEDUMMY)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) zadatak1.b.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(SIZEDUMMY) $(AVRDUDEDUMMY)

.PHONY: all clean dependents

-include ../makefile.targets
