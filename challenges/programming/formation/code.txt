def draw(height)
  (1..height).each do |i|
    puts " " * (height - i) + "*" * (2 * i - 1)
  end
end

def main
  height = 7
  draw(height)
end

if __FILE__ == $0
  main
end