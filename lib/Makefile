
#include $(utildir)/PubRule

pages_js = $(patsubst %.js,$(libdir)/data/%.js,$(wildcard *.js))
pages_css = $(patsubst %.css,$(libdir)/data/%.css,$(wildcard *.css))

SUBDIR =

$(libdir):
	mkdir -p $@

$(libdir)/data: $(libdir)
	mkdir -p $@

$(libdir)/data/%.js: %.js $(libdir)/data
	cp $< $@

$(libdir)/data/%.css: %.css $(libdir)/data
	cp $< $@

$(libdir)/data/fdl-data-debug.js: json2.js fdl-data-core.js fdl-data-context.js fdl-data-notification.js fdl-data-document.js fdl-data-documentlist.js fdl-data-collection.js fdl-data-documentfilter.js fdl-data-documentselection.js fdl-data-user.js fdl-data-attribute.js fdl-data-search.js fdl-data-documenthistory.js fdl-data-application.js fdl-data-action.js fdl-data-family.js fdl-data-workflow.js fdl-data-grouprequest.js $(libdir)/data
	cat json2.js fdl-data-core.js fdl-data-context.js fdl-data-notification.js fdl-data-document.js fdl-data-documentlist.js fdl-data-collection.js fdl-data-documentfilter.js fdl-data-documentselection.js fdl-data-user.js fdl-data-attribute.js fdl-data-search.js fdl-data-documenthistory.js fdl-data-application.js fdl-data-action.js fdl-data-family.js fdl-data-workflow.js fdl-data-grouprequest.js> $@

$(libdir)/data/json2.js: json2.js
	cp $< $@

$(libdir)/data/fdl-data.js: $(libdir)/data/fdl-data-debug.js
	php ../jsmin.php $< $@

publish: $(libdir)/data $(pages_js) $(pages_css) $(libdir)/data/fdl-data-debug.js $(libdir)/data/fdl-data.js
