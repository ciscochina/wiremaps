IMAGES=$(patsubst %.svg,%.png,$(wildcard port-*.svg col-*.svg))
WIDTH=30

all: stamp-ports
	$(MAKE) png
stamp-ports: port.svg
	./make-ports
	touch stamp-ports
png: $(IMAGES)
%.png: %.svg
	inkscape --file=$< --export-png=$@ -C \
		 --export-width=$(WIDTH)

clean:
	rm -f stamp-ports
	rm -f $(IMAGES) $(wildcard port-*.svg)

.PHONY: clean
