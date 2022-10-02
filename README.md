No- 👋 Hi, I’m @Reynosoluis
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Reynosoluis/Reynosoluis is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
@@ -26,15 +26,15 @@ def search(expression, data, runtime_options = {})
      data = case data	      data = case data
        when Hash, Struct then data # check for most common case first	        when Hash, Struct then data # check for most common case first
        when Pathname then load_json(data)	        when Pathname then load_json(data)
        when IO, StringIO then JSON.load(data.read)	        when IO, StringIO then JSON.parse(data.read)
        else data	     else data
        end	        end
      Runtime.new(runtime_options).search(expression, data)	      Runtime.new(runtime_options).search(expression, data)
    end	    end


    # @api private	    # @api private
    def load_json(path)	    def load_json(path)
      JSON.load(File.open(path, 'r', encoding: 'UTF-8') { |f| f.read })	      JSON.parse(File.open(path, 'r', encoding: 'UTF-8') { |f| f.read })
    end	    end
