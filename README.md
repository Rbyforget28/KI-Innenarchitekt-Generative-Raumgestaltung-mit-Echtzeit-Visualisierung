# KI-Innenarchitekt-Generative-Raumgestaltung-mit-Echtzeit-Visualisierung
KI-Innenarchitekt nutzt generative KI, um basierend auf den Vorlieben und Anforderungen des Nutzers individuelle Raumgestaltungen zu erstellen und diese in interaktiven 3D-Umgebungen zu visualisieren.
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
import random

def get_user_preferences():
    """
    Simulate getting user preferences for room design.
    Returns a dictionary of preferences.
    """
    # Example preferences
    return {
        'style': 'modern',
        'colors': ['blue', 'white'],
        'budget': 5000,
        'room_type': 'living room'
    }

def generate_design(preferences):
    """
    Simulate the generative AI design process based on user preferences.
    Returns a list of mock "furniture" positions and colors (representing design elements).
    """
    # Mockup design based on preferences (simplified for demo)
    design = {
        'furniture': [
            {'position': (random.uniform(0, 5), random.uniform(0, 5), 0), 'color': random.choice(preferences['colors'])} for _ in range(5)
        ]
    }
    return design

def visualize_design(design):
    """
    Visualize the room design in a basic 3D plot.
    """
    fig = plt.figure()
    ax = fig.add_subplot(111, projection='3d')
    
    # Plot furniture items
    for item in design['furniture']:
        ax.scatter(item['position'][0], item['position'][1], item['position'][2], color=item['color'], s=100)

    ax.set_xlabel('X')
    ax.set_ylabel('Y')
    ax.set_zlabel('Z')
    ax.set_title('Room Design Visualization')

    plt.show()

def main():
    preferences = get_user_preferences()
    design = generate_design(preferences)
    visualize_design(design)

if __name__ == "__main__":
    main()
