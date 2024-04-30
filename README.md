from PIL import Image, ImageDraw, ImageFont

def create_man_with_camera_face(image_size=(512, 512), background_color=(255, 255, 255), man_color=(0, 0, 0), camera_color=(255, 0, 0)):
    # Create a blank image with the specified background color
    image = Image.new("RGB", image_size, background_color)
    draw = ImageDraw.Draw(image)

    # Draw the man's body
    draw.rectangle([(200, 200), (300, 400)], fill=man_color)

    # Draw the man's head
    draw.ellipse([(200, 150), (300, 250)], fill=man_color)

    # Draw the camera as the man's face
    draw.rectangle([(220, 170), (280, 230)], fill=camera_color)
    draw.rectangle([(210, 160), (290, 240)], outline=man_color)

    return image

if __name__ == "__main__":
    # Create the image of the man with camera face
    man_with_camera_face = create_man_with_camera_face()

    # Save the image
    man_with_camera_face.save("man_with_camera_face.png")
    
